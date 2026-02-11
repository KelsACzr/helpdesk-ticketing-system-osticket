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
  
  - **Service Level Agreements (SLAs)**
    - Priority Levels & Resolution Times:
      - P1: Critical(2 hours) - Company-wide issues which impact reveneue i.e., Network, Server, or VPN outages that affect all in-house and remote staff.
      - P2: High(8 hours) - Department-specific issues, i.e., application errors, workstation issues, and email access issues.
      - P3: Normal(12 hours) - Non-critical issues affecting the end-users, i.e., access requests, workstation problems, printer issues.
      - P4: Low (24 hours) - For standard user/client requests, i.e., questions and minor changes.

- **Roles & Permissions** agent role assignment and department access configuration.
    
- **Structured Help Topics** - each topic was mapped to a specific department with its default SLA for ticket categorization
  - Password Reset
  - Email Issue
  - Network Connectivity
  - Unable to Print
  - Access Request
  - New Employee Onboarding
  - Feedback
  - General Inquiry

- **Ticket Workflow Configuration of Lifecycle Stages:**
  - Open
  - Assigned
  - Inprogress
  - On Hold
  - Resolved
  - Closed
 
## 1. System Configuration
The platform settings were configured via the Admin Panel. The purpose is to ensure consistency and standardization in the support environment.
[*Admin Panel → Settings*]

Fictional Company Name: Shopper's Rite LLC.

![company profile](screenshots/company%20profile.png)

The following **System** settings were applied; 
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
The structured departments were created under the Default Department: Support [*Admin → Agents → Departments*] - the Sales Team uses a separate mailbox.

![departments](screenshots/departments.png)

### 2.1 Service Level Agreements (SLAs)
The following SLAs were set and assigned to each department. [*Admin → Manage → SLA*]

![SLAs Set](screenshots/17%20SLAs%20Set.png)
  
- **SLAs by Department**
  - Technical Support → P2 – High (8 hours)
  - Network Support → P1 – Critical (2 hours)
  - Application Support → P2 – High (8 hours)
  - Sales → P3 – Normal (24 hours)

![tech support SLA](screenshots/Tech%20Support%20SLA.png)

### 2.2 Roles & Permissions (Access Control)
These 4 users were assigned permissions based on their role to demonstrate user privilege and operational control [*Admin → Staff → Roles*]
- Helpdesk Technician (Tecni)
- Senior Technician
- IT Manager
- Sales Executive


