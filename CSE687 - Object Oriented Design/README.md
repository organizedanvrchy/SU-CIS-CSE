>[!NOTE]
>__Project done in collaboration with [Pedro Ortiz](https://github.com/Pjortiz13) and [Joe Laible](https://github.com/JoeLaible123).__ <br>
>This is a re-upload and edited version from the original as forking to this repository was not possible and submodules would not make much difference as this repository is simply deprecated. 

---

# Project Phase 1 - MapReduce 
The MapReduce project is a standalone command line program written in C++ and developed using visual studios. The project responsibilites were split equally between the team and team members used github to edit, 
commit, and share ideas. <br> 
The code includes classes for handling file management, _'fileManagement.h/cpp'_, mapping, _'map.h/cpp'_, reducing, _'reduce.h/cpp'_, and to orchestate the mapreduce worlflow, _'workflow.h/cpp'_. The program processes shakesspearts in a text file to perform a word count opeartion, storing intermediate and final results in user specfied directories.

### HOW TO RUN:
1. Compile the source code using C++ compiler:

```
g++ -o MapReduceProgram executive.cpp workflow.cpp map.cpp reduce.cpp fileManagement.cpp -std=c++17
```

2. Generate three folders: first folder with the shakespeare.txt files named 'testinput', second folder labeled 'testoutput' and a third folder named 'testtemp'

>[!NOTE]
>If a different folder name is wanted, changes to the map.cpp and reduce.cpp files are needed

3. Execute the compiled program via the commandline using the format below:

```
.\MapReduceProgram "<input directory>" "<output directory>" "<temporary directory>" replace <input directory> , <output directory> , and <tempoary directory> 
```

with the file paths to their respective directories.

Example: 
```
.\MapReduceProgram "D:\school\2024\Spring 2024\Object Oriented Design\map_reduce_main_working_2\testinput" "D:\school\2024\Spring 2024\Object Oriented Design\map_reduce_main_working_2\testoutput" "D:\school\2024\Spring 2024\Object Oriented Design\map_reduce_main_working_2\testtemp"
```

4. Once the program has executed succesfully within the <output directory>, the final word count results and a success file will be generated, along with a .txt file within the testtemp folder that should hold the intermediate output. 

---

# Project Phase 2 - MapReduce DLL
This phase uses a client program written in C++ that calls in the Map and Reduce DLLs to carry out the MapReduce functionality. The code includes two DLLs, one that carries out the Map function and the other that carries out the Reduce function, along with a client app that contains the 'fileManagement.h/cpp' and 'workflow.h/cpp'. Similar to Phase 1, the program processes a directory of Shakespeare's works in text files, performs a word count operation, and stores the intermediate and final results in user specified directories. As per Phase 1, the project responsibilites were split equally between the team and team members used github to edit, commit, and share ideas. 

### HOW TO RUN:
1. Download the MapReduce, libMap, and libReduce folders from the GitHub.

2. Enter directory located at ..\..\MapReduce\x64\Debug (NOT ..\..\MapReduce\MapReduce\x64\Debug) and generate three folders. T
he first folder is named 'testinput', which contains the Shakespeare .txt files (this folder may already exist in this project); the second folder is 
labeled 'testoutput', which holds the final output of the program; and a third folder named 'testtemp'.

>[!NOTE]
>If a different folder name is wanted, then changes to the source files of the Map and Reduce libraries are necessary.

3. Open the command prompt (preferably as Admin) and navigate to the directory that contains "MapReduce.exe". This can be done by using the command below: 

```
cd C:\..\..\MapReduce\x64\Debug
```
>[!NOTE]
>C:\\..\\..\ should be replaced with appropriate file path. <br>
For example: C:\SU\Phase_2\MapReduce\x64\Debug 

>[!TIP]
>Use command "dir" to check current directory for MapReduce.exe and also ensure that libMap.dll and libReduce.dll are present.

4. Execute the client program via the command line using the format below:

```
MapReduce.exe "<input directory>" "<output directory>" "<temporary directory>"
```

>[!NOTE]
>Replace "input directory", "output directory", and "tempoary directory" with the names of the folders.

>If using the default names, then use the format below:
> ```
> MapReduce.exe "testinput" "testoutput" "testtemp"
> ```

5. Once the program has executed succesfully, the final word count results will be within the <output directory> as well as a .txt file named "SUCCESS". 
Additionally, a .txt file is generated within the "testtemp" folder that should hold the intermediate output. 

---

# Project Phase 3:
In Phase 3, the MapReduce implementation was extended to support multiple mappers and reducers to handle larger datasets and improve performance. The enhancements include the creation of a partition function that splits keys into R buckets, with R being the number of reducer processes.

### HOW TO RUN:
1. Download the Updated Folders:
	- Ensure you have the latest MapReduce, libMap, and libReduce folders from GitHub.
2. Directory Setup:

	- Create three directories:
		- testinput for input files.
		- testoutput for final results.
		- testtemp for intermediate files.

3. Configure Command-Line Arguments in Visual Studio:

	- Right-click on the MapReduce project.
	- Select Properties.
	- Navigate to Configuration Properties -> Debugging.
	- Set Command Arguments to the paths of the directories created as: <br>
```
"D:\school\2024\Spring 2024\Object Oriented Design\testinput" "D:\school\2024\Spring 2024\Object Oriented Design\testoutput" "D:\school\2024\Spring 2024\Object Oriented Design\testtemp"
```

4. Build and run the project
	- Press 'F5' in visual studio to compiule and ru the program with the arguments specified above.

5. Expected Results:
	- Intermediate output:
		- within the testtemp directory should show 4 mappers and 4 reducers files that were from the mapper and reduce processes.
		- within the testoutput directory should contain 2 files 1 for results.txt and SUCESSS.txt.

---

# Project Phase 4:
In Phase 4, the MapReduce implementation was reconfigured to support a controller-stub process. _This phase was unable to be completed_, the intent was to develop a heartbeat stream between stub and controller to coordinate the running of the Map and Reduce processes. This attempt was utilizing sockets to communicate between stub and controller. 

### HOW TO RUN:
1. Download the Updated Folders:
	- Ensure you have the latest Worfklow,Stub,Controller, MapReduce, libMap, and libReduce folders from GitHub.

2. Directory Setup:
	- Create three directories:
		- testinput for input files.
		- testoutput for final results.
		- testtemp for intermediate files.

3. Configure Command-Line Arguments in Visual Studio:
	- Right-click on the MapReduce project.
	- Select Properties.
	- Navigate to Configuration Properties -> Debugging.
	- Set Command Arguments to the paths of the directories created:
```
"D:\school\2024\Spring 2024\Object Oriented Design\testinput" "D:\school\2024\Spring 2024\Object Oriented Design\testoutput" "D:\school\2024\Spring 2024\Object Oriented Design\testtemp"
```

4. Build and run the project
	- press 'F5' in visual studio to compiule and rum the program with the arguments specified above
	- To run via command line, please initiate the sequence in the following order:
		- Stub.exe
		- Controller.exe 
		- Mapreduce.exe 

5. Current Results:
	- Controller.exe will produce messages confirming the sending and receiving of messages between itself and stub. 

---

# Current state 
Problem set was unable to be solved, current solution only facilitates heartbeat messages between Stub and controller, there is no initialization of child processes to run the map and reduce process. Continuation of the project should look into the initialization of map and reduce processes based on reception of relevant messages from the controller (-last attempted methodology). 
