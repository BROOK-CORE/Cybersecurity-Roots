# Cybersecurity Architecture: Roles and Tools

## 1. Cybersecurity Architecture

Cybersecurity architecture is the design of security controls and technologies across an organization's systems.

It connects security requirements with:

- Business requirements
- Applications
- Data
- Networks
- Endpoints
- Identity systems
- Monitoring
- Incident response

The goal is to build security into the system instead of adding it after deployment.

## 2. Cybersecurity Architect

A cybersecurity architect considers:

- What must be protected
- How a system could fail
- Possible threats
- Attack entry points
- Required security controls
- How controls work together
- How security changes as a system grows

An IT architect asks how a system should work. A security architect also asks how it could fail or be attacked and how to reduce those risks.

## 3. Security by Design

A typical lifecycle is:

```text
Requirements
    ↓
Architecture
    ↓
Design
    ↓
Implementation
    ↓
Testing
    ↓
Deployment
    ↓
Monitoring
```

Security should be considered throughout the lifecycle.

## 4. Defense in Depth

Defense in depth uses multiple security layers.

```text
Internet
   ↓
Firewall
   ↓
Web Protection
   ↓
Network Segmentation
   ↓
Authentication
   ↓
Authorization
   ↓
Database Controls
   ↓
Encryption
   ↓
Monitoring
```

If one control fails, another layer may reduce the impact.

## 5. Least Privilege

Least privilege means giving users, applications, and systems only the permissions they require.

Example:

```text
Application
    ↓
Can read required records
    ↓
Cannot delete unrelated records
    ↓
Cannot administer the operating system
```

This limits the damage from compromised accounts, applications, malware, and mistakes.

## 6. CIA Triad

```text
Confidentiality
Integrity
Availability
```

### Confidentiality

Only authorized users or systems should access information.

Common controls:

- Authentication
- Authorization
- Encryption
- Permissions

### Integrity

Information should remain accurate and protected from unauthorized modification.

Common controls:

- Hashes
- Digital signatures
- Logging
- Integrity checks

### Availability

Authorized users should be able to access systems when required.

Common controls:

- Redundancy
- Failover
- Monitoring
- Capacity planning
- DDoS protection

## 7. Major Security Domains

```text
                 Cybersecurity
                      |
       --------------------------------
       |       |       |       |      |
      IAM   Endpoint  Network  App    Data
       |       |       |       |      |
     Users   Devices Traffic  Code Information
```

Security monitoring connects these domains.

## 8. Identity and Access Management

IAM controls who can access resources and what they can do.

It commonly includes:

- Authentication
- Authorization
- Account management
- Role management
- Privileged access
- Multi-factor authentication

Flow:

```text
User
 ↓
Authentication
 ↓
Identity confirmed
 ↓
Authorization
 ↓
Permission decision
 ↓
Resource access
```

Authentication asks:

> Who are you?

Authorization asks:

> What are you allowed to do?

## 9. Multi-Factor Authentication

MFA uses multiple authentication factors.

Examples:

```text
Password
+
Authenticator application
```

```text
Password
+
Security key
```

The objective is to avoid relying on a single credential.

## 10. Privileged Access

Privileged accounts can make high-impact changes.

Examples:

- System administrator
- Database administrator
- Cloud administrator
- Security administrator

Useful protections include:

- MFA
- Strong authentication
- Limited privileges
- Separate administrator accounts
- Session monitoring
- Access logging

## 11. Endpoint Security

Endpoints include:

- Laptops
- Desktops
- Servers
- Mobile devices
- Virtual machines

Endpoint security can include:

- Anti-malware
- Endpoint detection and response
- Patch management
- Device control
- Host firewalls
- Disk encryption
- Configuration management

## 12. Network Security

Network security protects communication between systems.

Important areas include:

- Firewalls
- Network segmentation
- Secure protocols
- Intrusion detection
- Intrusion prevention
- Network monitoring
- Access control

Example:

```text
Internet
   |
Firewall
   |
DMZ
   |
Internal Network
   |
Sensitive Systems
```

## 13. Network Segmentation

Segmentation separates systems into different security zones.

```text
           Internet
               |
           Firewall
               |
       -----------------
       |               |
     DMZ          Internal LAN
                       |
                ----------------
                |              |
             Employees      Database
```

Segmentation can limit lateral movement after a compromise.

## 14. Application Security

Application security protects software throughout its lifecycle.

Important areas:

- Secure coding
- Input validation
- Authentication
- Authorization
- Dependency management
- Vulnerability testing
- Secure configuration
- Security testing

## 15. Data Security

Data security protects information throughout its lifecycle.

```text
Create
  ↓
Store
  ↓
Use
  ↓
Transfer
  ↓
Archive
  ↓
Delete
```

Controls can include:

- Encryption at rest
- Encryption in transit
- Access control
- Data classification
- Backups
- Data loss prevention
- Secure deletion

## 16. Encryption

```text
Plaintext
   ↓
Encryption
   ↓
Ciphertext
   ↓
Decryption
   ↓
Plaintext
```

Encryption can protect data at rest and in transit.

## 17. Security Monitoring

Security monitoring collects and analyzes activity from:

- Firewalls
- Servers
- Applications
- Endpoints
- Identity systems
- Network devices
- Cloud services

Example:

```text
Firewall logs
       Server logs
        Endpoint logs ---> Monitoring Platform ---> Analyst
        /
IAM logs
```

## 18. SIEM

A SIEM can collect and correlate security-related events.

```text
Logs
 ↓
Collection
 ↓
Normalization
 ↓
Correlation
 ↓
Alert
 ↓
Investigation
```

Example:

```text
10 failed logins
      +
Successful login
      +
Unusual location
      +
Sensitive file access
      ↓
Potential suspicious activity
```

## 19. Detection and Response

Security architecture should support:

```text
Prevent
  ↓
Detect
  ↓
Investigate
  ↓
Contain
  ↓
Recover
```

Prevention may fail, so monitoring and response are important additional layers.

## 20. Security Frameworks

Frameworks provide structured ways to organize security work.

They can help organizations:

- Identify risks
- Define security activities
- Organize controls
- Measure improvements
- Assign responsibilities

## 21. Architecture Diagrams

Architecture diagrams help reveal:

- Trust boundaries
- Critical assets
- Entry points
- Data flows
- Security controls
- Dependencies

Example:

```text
Users
  |
Internet
  |
Firewall
  |
Web Application
  |
Application API
 /           \
Database    Identity
          Logs
      |
Monitoring
```

## 22. Threat Modeling

Threat modeling asks what could go wrong before deployment.

```text
Identify assets
      ↓
Identify entry points
      ↓
Identify threats
      ↓
Evaluate risk
      ↓
Select controls
      ↓
Review architecture
```

Questions:

- What are we protecting?
- Who might attack it?
- How could they reach it?
- What could they do?
- What would the impact be?
- How can the risk be reduced?

## 23. Trust Boundaries

A trust boundary separates systems or components with different trust levels.

```text
Internet
   |
   | Untrusted
   |
----------- Trust Boundary ----------
   |
Application
   |
----------- Trust Boundary ----------
   |
Database
```

Security controls should be considered when data crosses a trust boundary.

## 24. Security Controls

### Preventive

Designed to stop unwanted events.

Examples:

- Firewalls
- Access controls
- MFA
- Encryption

### Detective

Designed to identify suspicious activity.

Examples:

- Monitoring
- Intrusion detection
- Logging
- Alerts

### Corrective

Designed to restore or correct systems.

Examples:

- Recovery
- Restoration
- Remediation
- Reconfiguration

A mature architecture uses multiple control types.

## 25. Security Architecture Principles

### Least Privilege

Give only required permissions.

### Defense in Depth

Use multiple security layers.

### Secure by Design

Include security during architecture and development.

### Separation of Duties

Avoid giving one person complete control over sensitive processes when practical.

### Fail Securely

A failure should avoid creating unnecessary security exposure.

### Minimize Attack Surface

Reduce unnecessary:

- Services
- Ports
- Interfaces
- Accounts
- Permissions
- Exposed applications

## 26. Example Secure Architecture

```text
                         Internet
                            |
                       DDoS Protection
                            |
                         Firewall
                            |
                    Web Protection
                            |
                         Web Tier
                            |
                    Application Tier
                     /            \
                IAM Service       API
                    |             |
                    |          Database
                    |
                 MFA / SSO
                    |
                User Devices
                    |
             Endpoint Security
                    |
              Security Monitoring
                    |
                   SIEM
                    |
              Security Analysts
```

Security is distributed across the architecture instead of being concentrated in one product.

## 27. Architecture vs. Product Collection

A collection of security products does not automatically create a secure architecture.

Even with:

```text
Firewall
Antivirus
SIEM
MFA
Encryption
```

security can still be weak when:

- Controls are misconfigured
- Important systems are uncovered
- Permissions are excessive
- Alerts are ignored
- Network design is poor
- Sensitive data is exposed
- Controls do not work together

Architecture is about how the pieces fit together.

## 28. Security Architect Mindset

Ask:

```text
What are the critical assets?

Where are they located?

Who can access them?

How does data move?

Where are the trust boundaries?

What happens if an account is compromised?

What happens if an endpoint is compromised?

What happens if the application is attacked?

How will we detect it?

How will we contain it?

How will we recover?
```

## 29. Key Takeaways

```text
Cybersecurity architecture
        ↓
Security by design
        ↓
Multiple security layers
        ↓
Strong identity and access controls
        ↓
Protected endpoints
        ↓
Segmented networks
        ↓
Secure applications
        ↓
Protected data
        ↓
Continuous monitoring
        ↓
Detection and response
```

Security should be designed into the architecture from the beginning and maintained throughout the system lifecycle.
