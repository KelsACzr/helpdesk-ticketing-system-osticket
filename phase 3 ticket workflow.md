![osTicket Logo File](screenshots/osTicket-Logo.png)

# Phase 3: Ticket Lifecycle & Resolution Workflow

This phase simulated a real-world Technical Support environment and demonstrated ticket intake, prioritization, assignment, troubleshooting, documentation, and resolution. 

## Environments & Technologies
- Oracle VirtualBox
- Internet Information Services (IIS)
## Operating System
- Windows Server 2022 (21H2) | Build 20348.587
  
## Ticket Lifecycle Overview

![Ticket Lifecycle Overview](screenshots/Ticket%20Lifecycle%20Overview.png)

### 1. Ticket Submission (Client Portal)
The client visited the Guest Portal to submit their query.

![client submission](screenshots/client%20submission.png)
![client submission success](screenshots/client%20submission%20success.png)


- **Issue**: A standard user is unable to log into their workstation after multiple failed attempts.


### 2. Automatic Routing (Help Topic → Department)

The preset help topic, "Password Reset," automatically routed the ticket to the Technical Support Team.

- **Help Topic**: Report a Problem >  Access Issue >  Password Reset
- **Department**: Support/Techcnical Support

![ticket routed](screenshots/ticket%20routed.png)


### 3. SLA Assignment (Based on Priority)

Based on the previously set SLA Plan in [Phase 2 - Configuration & Operational Readiness](https://github.com/KelsACzr/helpdesk-ticketing-system-osticket/blob/7c1c4dc61c5a1da4b193f6eeec68c6b649587df8/phase-2-configuration.md) this scenario was categorized as follows:

- **SLA Validation**:
	- A single user was affected.
	- There were no security breaches detected.
	- All other users and departments were functional.
  - This issue does not impact the company financially. 

- **SLA Assignment**: P3: Normal(12hrs)

![priority normal](screenshots/priority%20normal.png)

The ticket was then automatically assigned to an agent after sending the initial reply to the user.

![ticket assigned to tech](screenshots/ticket%20assigned%20to%20tech.png)

### 4. Troubleshooting > Documentation > Resolution > Closure

The user's identity was validated using the internal verification procedure. i.e., the user was contacted via their internal extension: 342 to verify their internal Employee ID and date of birth. 

- **Name**: Oscar Jameson
- **Domain**: SHOPPERSRITE
- **Username**: OJAMESON
- **Employee ID**: **SR-OJ-9985**
- **Department**: Sales

Active Directory was used to confirm the account status. The user's password was reset successfully. *“User must change password at next login.”* was enabled. The user was advised in the following response:

![resolution response](screenshots/resolution%20response.png)

Each step of the process was documented and entered into the osticket Knowledgebase for use by the Technical Support Team. 

- **Topic**: "Workstation Password Reset Procedure."
- **Category**: Internal – Technical Support
- **Applies To**: Domain-Joined Workstations (Active Directory Environment)

![procedure documented](screenshots/procedure%20documented.png)

After the user confirmed that they were able to log in successfully, the ticket status was changed to *'Resolved'* and the appropriate notes were added.

![res notes](screenshots/res%20notes.png)


