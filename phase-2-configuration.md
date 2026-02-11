![osTicket Logo File](screenshots/osTicket-Logo.png)

# Phase 2: Configuration & Operational Readiness
This section explains the post-installation configuration steps for osTicket, where the platform was taken from a new installation to a fully functional, multi-department helpdesk environment by implementing role-based access control, SLA plans, ticket categorization, and workflow management to simulate real-world Technical Support Operations.

## Environments & Technologies
- Oracle VirtualBox
- Internet Information Services (IIS)
## Operating System
- Windows Server 2022 (21H2) | Build 20348.587

## Configuration Tasks
- **System Configuration:** Company name, default department, ticket settings, date, and timezone configuration.
- **Department Structure for Ticket Routing:**
  -  Technical Support
  -  Network Support
  -  Application Support
  -  Sales
 
- **Role-Based Access Control (RBAC)**
- **Service Level Agreements (SLAs)**
  - Priority Levels & Resolution Times:
    - P1: Critical(2 hours)
    - P2: High(8 hours)
    - P3: Normal(24 hours)
    - P4: Low (48 hours)
    
- **Structured Help Topics** - each topic was mapped to a specific department with its default SLA for ticket categorization
  - Password Reset
  - Email Issue
  - Network Connectivity
  - Unable to Print
  - Access Request
  - New Employee Onboarding
  - Feedback
  - General Inquiry
    
- **Agent Setup** - role assignment and department access configuration.
  - Super Admin
  - Standard User 

- **Ticket Workflow Configuration of Lifecycle Stages:**
  - Open
  - Assigned
  - Inprogress
  - On Hold
  - Resolved
  - Closed
 
## 1. System Configuration
The platform settings were configured via the Admin Panel. The purpose is to ensure consistency and standardization in the support environment.
[*Admin Panel → Settings → System*]

The following settings were applied; 
- Helpdesk Name: Helpdesk Lab v1.0
- Default Department: Support
- Default Time Zone: America / New_ York
- Date & Time Format: Locale Defaults
- Default Schedule:  Monday - Friday 8 am-5 pm with U.S. Holidays

![osticket local settings](screenshots/osticket%20local%20settings.png)

Next, the Ticket Settings were configured as follows: [*Admin Panel → Settings → Tickets*]

- Default Ticket Number format: HDLV1##
- Default Ticket Number Sequence: General Tickets with an increment of 1

![osticket sequence](screenshots/osticket%20sequence.png)

- Default Status: Open
- Default Priority: Normal
- Default SLA: Level 4 - Low (24 Hours - Active)
- Default Help Topic: General Inquiry
- Maximum Open Tickets: 5
- Human Verification: Enabled -  to avoid time wastage on spammy or potentially dangerous tickets

![osticket ticket settings](screenshots/osticket%20settings.png)

## 2. Department Structure for Ticket Routing
