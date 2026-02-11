![osTicket Logo File](screenshots/osTicket-Logo.png)

# Phase 2: Configuration & Operational Readiness
This section explains the post-installation configuration steps for osTicket, where the platform was taken from a new installation to a fully functional, multi-department helpdesk environment by implementing role-based access control, SLA plans, ticket categorization, and workflow management to simulate real-world Technical Support Operations.

## Environments & Technologies
- Oracle VirtualBox
- Internet Information Services (IIS)
## Operating System
- Windows Server 2022 (21H2) | Build 20348.587

## Configuration Tasks
- **1. System Configuration:** Company name, default department, ticket settings, date, and timezone configuration.
  
- **2. Roles & Permissions:** user role assignment and department access configuration.
  
- **3. Department Structure for Ticket Routing:**
  -  Technical Support
  -  Network Support
  -  Application Support
  -  Sales

- **4. Structured Help Topics** - the following topics were listed:
  - Password Reset
  - Email Issue
  - Network Outage
  - Unable to Print
  - Access Request
  - New Employee Onboarding
  - Feedback
  - General Inquiry
  - VPN Outage

- **5.Service Level Agreements (SLAs)**
    - Priority Levels & Resolution Times:
      - P1: Critical(2 hours) - Company-wide issues which impact reveneue i.e., Network, Server, or VPN outages that affect all in-house and remote staff.
      - P2: High(8 hours) - Department-specific issues, i.e., application errors, workstation issues, and email access issues.
      - P3: Normal(12 hours) - Non-critical issues affecting the end-users, i.e., access requests, workstation problems, printer issues.
      - P4: Low (24 hours) - For standard user/client requests, i.e., questions and minor changes.
     
- **6. User Onboarding**
  - A new user [Jane Mollineau] was configured for the Tier 1 Technical Support Team.
      
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


## 2. Roles & Permissions (Access Control)
These 4 roles were assigned permissions based on their department to demonstrate user privilege and operational control [*Admin → Staff → Roles*]
- **Helpdesk Technician (Tier 1 Support)**:  Can handle tickets assigned to the Technical Support Department only. No access to make advanced changes.
- **Senior Technician (Tier 2 Support)**: Handles escalated queries assigned to the Technical Support Department only, without full access.
- **IT Manager (Administrator Level)**:  Full Access to all permissions across all departments.
- **Sales Executive**: Can handle tickets assigned to the Sales Department only.

![Senior Tech Access](screenshots/Tier%202%20%20Ticket%20Permissions.png)

![All roles osticket](screenshots/All%20roles%20osticket.png)

## 3. Department Structure for Ticket Routing
The structured departments were created under the Default Department: Support [*Admin → Agents → Departments*] - the Sales Team uses a separate mailbox.

![departments](screenshots/departments.png)

The relevant teams were then created to facilitate ticket assignments. [*Admin → Agents → Teams*]

![teams created](screenshots/teams%20created.png)

## 4. Structured Help Topics

To ensure that all new help topics are accurately assigned and categorized, a **Parent Topic** was assigned, and **Department** was assigned. The appropriate **Priority** and **SLA Plans** were configured, and the **Auto-Assign** was configured for the relevant department.  [*Admin → Manage → Help Topics*]

![new topic](screenshots/new%20help%20topic.png)

The end-user will then access the Support Centre to open a new ticket and select the appropriate help topic using the URL: http://localhost/osTicket/

![support center topics](screenshots/end%20-user%20help%20topics.png)

## 5. Service Level Agreements (SLAs)
The following SLAs were set and assigned to each department. [*Admin → Manage → SLA*]

![SLAs Set](screenshots/17%20SLAs%20Set.png)
  
### 5.1 SLAs by Department
  - Technical Support → P2 – High (8 hours)
  - Network Support → P1 – Critical (2 hours)
  - Application Support → P2 – High (8 hours)
  - Sales → P3 – Normal (24 hours)

![tech support SLA](screenshots/Tech%20Support%20SLA.png)

## 6. User Onboarding

**Credentials**
- User 'Jane Mollineau' was created. [*Admin → Agents → Agents*]
- Username: jmollineau
- Password: Sent to the User's Email

![jane creds](screenshots/Jane%201.png)

**Jane's Access Level**
- Department: Support/ Technical Support
- Role: Helpdesk Technician (Tier 1 Support)

![jane access](screenshots/Jane%202.png)

**Jane's Permissions**
This account was configured for limited permissions to make any major changes. 

![jane permissions 1](screenshots/Jane%20Permissions%201.png)

![jane permissions 2](screenshots/Jane%20Permissions%202.png)

![jane permissions 3](screenshots/Jane%20Permissions%203.png)

**Jane's Team Assignment**
- Jane was assigned to the Team: "T1 Technical Support"
![jane team assign](screenshots/Jane%20Team%20Assignment%203.png)

## Final Considerations
- User Session Timeout: the *User Session Timeout* was changed from 30 minutes to 0 to avoid having to sign in again and encounter the error shown below;

![osticket login error](screenshots/osticker%20login%20error.png)

![user session timeout](screenshots/User%20Session%20Timeout.png)



