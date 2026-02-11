![osTicket Logo File](screenshots/osTicket-Logo.png)

# Phase 2: Configuration & Operational Readiness
This section explains the post-installation configuration steps for osTicket, where the platform was taken from a new installation to a fully functional, multi-department helpdesk environment by implementing role-based access control, SLA plans, ticket categorization, and workflow management to simulate real-world Technical Support Operations.

## Environments & Technologies
- Oracle VirtualBox
- Internet Information Services (IIS)
## Operating System
- Windows Server 2022 (21H2) | Build 20348.587

## 1. Configuration Tasks
- System Configuration: Company name, branding, date, and timezone configuration.
- Department Structure for ticket routing:
  -  Technical Support
  -  Network Support
  -  Application Support
  -  Sales
 
- Role-Based Access Control (RBAC)
- Service Level Agreements (SLAs)
  - Priority Levels & Resolution Times:
    - P1: Critical(2 hours)
    - P2: High(8 hours)
    - P3: Normal(24 hours)
    - P4: Low (48 hours)
    
- Structured Help Topics - each topic was mapped to a specific department with its default SLA for ticket categorization
  - Password Reset
  - Email Issue
  - Network Connectivity
  - Unable to Print
  - Access Request
  - New Employee Onboarding
  - Feedback
  - General Inquiry
    
- Agent Setup - role assignment and department access configuration.
- Ticket Workflow Configuration
