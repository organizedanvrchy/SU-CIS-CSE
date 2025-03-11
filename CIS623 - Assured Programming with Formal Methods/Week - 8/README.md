# Security Mechanisms and Security Policies

## Security Mechanisms
### Access Control List (ACL)
- A list of **principals** (users, processes) and their **access rights** to protected objects.
- Managed by **reference monitors** that enforce access policies.
- Components:
  - **Access Policy**: Defines authority, subject controls, access rights, and objects.
  - **Trust Assumption**: `ACL => Authority` (ACLs derive authority from trusted entities).
- **Access Request Structure**:  
  `subject says (access right, object)`.
- Related to **Access Control Matrix** (referenced as ACST Table 4.1).

## CIA Triad
The three pillars of security:
- **Confidentiality**: Ensures information/resources are inaccessible to unauthorized entities (e.g., secrecy).
- **Integrity**: Ensures data accuracy and trustworthiness (e.g., verifying data sources and preventing corruption).
- **Availability**: Maintains minimum performance/service quality (e.g., resilience to DoS attacks).

---

## Security Policies
### Discretionary Security Policies (DAC)
- **Dynamic** and identity-based (IBAC: Identity-Based Access Control).
- Structure:  
  `Principal says (Subject controls (operation, object))`.
- **Discretionary Nature**:  
  `Principal controls (Subject controls (operation, object))`.
- **Vulnerabilities**: Susceptible to Trojan horses due to decentralized control.

### Mandatory Security Policies (MAC)
- **Static**, system-wide policies enforced by OS/hardware.
- Focus areas:
  - **Military**: Prioritizes **confidentiality** (e.g., Bell-La Padula Model).
  - **Commercial**: Prioritizes **integrity** (protecting systems from unauthorized modifications).
- **Bell-La Padula Model**: A formal model for enforcing confidentiality via "no read up, no write down" rules.
