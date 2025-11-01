<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This document captures the administrative configuration of a freshly installed osTicket instance, focusing on roles, departments, teams, user/agent onboarding, SLAs, and help topics. Screenshots illustrate each change for reproducibility and auditability.

---

<h2>Environment & Technologies</h2>

- Microsoft Azure VM (Windows Server / IIS)
- osTicket (Admin Panel and Agent Panel)
- Browser access to:
  - Admin/Analyst: <code>http://localhost/osTicket/scp/login.php</code>
  - End-User Portal: <code>http://localhost/osTicket</code>

---

<h2>Operating Systems Used</h2>

- Windows 10 Enterprise N </b> (22H2)

---

<h2>Configuration Objectives</h2>

- Define permission model with Roles
- Establish Departments and cross-department Teams
- Set end-user registration policy
- Create Agents (staff) and Users (customers)
- Implement SLA Plans (Sev-A/B/C)
- Publish Help Topics for user ticket intake

---

<h2>Configuration Steps</h2>


<!-- STEP 1: Roles -->
<p>
<strong>Step 1 – Configure Roles (Permissions):</strong><br/>
Admin Panel → Agents → Roles → <em>Add New Role</em>.<br/>
Create <strong>Supreme Admin</strong> with full permissions (Tickets, Tasks, Knowledgebase, Directory, etc.). Roles group permissions that can be applied across agents for consistent access control.
</p>
<p>
<img src="https://i.imgur.com/YybCmEi.png" height="80%" width="80%" alt="Before Admin Setup"/>

Access osTicket Admin Panel → Agents → Roles
  
<img src="https://i.imgur.com/6qWOguv.png" height="80%" width="80%" alt="Make Supreme Admin"/>

Access New Role & create a new role for Supreme Admin
  
<img src="https://i.imgur.com/pjjuoEL.png" height="80%" width="80%" alt="Tickets"/>
<img src="https://i.imgur.com/eojVXCk.png" height="80%" width="80%" alt="Tasks"/>
<img src="https://i.imgur.com/aVe8Gzy.png" height="80%" width="80%" alt="Knowledgebase"/>

Assign Supreme Admin with all Permissions within Tickets, Tasks, & Knowledgebase

<img src="https://i.imgur.com/MD3nCTS.png" height="80%" width="80%" alt="Verify Supreme Admin Created"/>

Verify Supreme Admin Role Created

</p>
<br />

<!-- STEP 2: Departments -->

<p>
<strong>Step 2 – Configure Departments:</strong><br/>
Admin Panel → Agents → Departments → <em>Add New Department</em>.<br/>
Create <strong>SysAdmins</strong>. Departments scope ticket visibility, SLAs, and routing defaults, enabling separation of duties (Help Desk vs. SysAdmins vs. Networking).
</p>
<p>
<img src="https://i.imgur.com/wugr3Y4.png" height="80%" width="80%" alt="Departments before setup"/>

Access Departments from Admin Panel → Agents → Departments

<img src="https://i.imgur.com/95P5RN4.png" height="80%" width="80%" alt="Make SysAdmin"/>

Add a new SysAdmin Department

<img src="https://i.imgur.com/qVF8xqe.png" height="80%" width="80%" alt="Verify SysAdmin Created"/>

Verify SysAdmin Department has been Created

</p>
<br />

<!-- STEP 3: Teams -->

<p>
<strong>Step 3 – Configure Teams (Cross-Dept):</strong><br/>
Admin Panel → Agents → Teams → <em>Add New Team</em>.<br/>
Create <strong>Online Banking</strong> and pull agents from multiple departments as needed. Teams enable cross-functional collaboration without changing departmental structure.
</p>
<p> 
<img src="https://i.imgur.com/72wNMQN.png" height="80%" width="80%" alt="Before Making Online Banking Team"/>

Access Teams through the Admin Panel → Agents → Teams to make a new Team
  
<img src="https://i.imgur.com/pzAbUbe.png" height="80%" width="80%" alt="Make New Team"/>

Access New Team to create New Online Banking Team

<img src="https://i.imgur.com/L661qUC.png" height="80%" width="80%" alt="Verify Online Banking Created"/>

Verify Online Banking Team has been Created
</p>
<br />

<!-- STEP 4: User Registration Policy -->

<p>
<strong>Step 4 – End-User Ticket Policy:</strong><br/>
Admin Panel → Settings → User Settings.<br/>
Set policy per lab requirement. For example, <em>Registration Required</em>: require users to register and log in to create tickets (i.e., do <strong>not</strong> allow unregistered users to create tickets). This enforces identity and improves traceability.
</p>
<p>
  <img src="https://i.imgur.com/JCOxhAo.png" height="80%" width="80%" alt="User settings registration policy"/>

Adjust Settings to match whether accounts will need to be registered to make Tickets
  
</p>
<br />

<!-- STEP 5: Agents -->

<p>
<strong>Step 5 – Create Agents (Staff):</strong><br/>
Admin Panel → Agents → <em>Add New</em>.<br/>
Add <strong>Jane</strong> (Dept: SysAdmins; Role: Supreme Admin or appropriate role).<br/>
Add <strong>John</strong> (Dept: Support; assign suitable role).<br/>
Agents handle tickets; roles and departments control what they can see and do.
</p>
<p>
  <img src="https://i.imgur.com/8IdRefF.png" height="80%" width="80%" alt="Before making Agents"/>

Access the Agent List from Admin Panel → Agents to make a new Agent
  
  <img src="https://i.imgur.com/j77Gyvx.png" height="80%" width="80%" alt="Making Jane"/>

Access Add New Agent to set Name and Email of Agent from here click Set Password to give Agent a password (Jane)

<img src="https://i.imgur.com/1jTRO5Y.png" height="80%" width="80%" alt="Set Password Jane"/>

Give Jane a Password for her Account

<img src="https://i.imgur.com/8RpU1t6.png" height="80%" width="80%" alt="Set Access for Jane"/>

Set Access for Jane to be SysAdmin Departmnet with Supreme Admin Role

<img src="https://i.imgur.com/RFQciE7.png" height="80%" width="80%" alt="Set Team for Jane"/>

Access Add New Agent to set Name and Email of Agent from here click Set Password to give Agent a password (John)

<img src="https://i.imgur.com/8IdRefF.png" height="80%" width="80%" alt="Set Password John"/>

Give John a Password for his Account

</p>
<br />

<!-- STEP 6: Users -->

<p>
<strong>Step 6 – Create Users (Customers):</strong><br/>
Agent Panel → Users → <em>Add New</em>.<br/>
Add <strong>Karen</strong> and <strong>Ken</strong> as end users. Users are ticket requesters; creating test users helps validate intake, notifications, and workflow.
</p>
<p>
  <img src="YOUR_IMAGE_LINK" height="80%" width="80%" alt="Create Users"/>
</p>
<br />

<!-- STEP 7: SLAs -->

<p>
<strong>Step 7 – Configure SLA Plans:</strong><br/>
Admin Panel → Manage → SLA → <em>Add New</em>.<br/>
Create <strong>Sev-A</strong> (Grace: 1 hour; Schedule: 24/7).<br/>
Create <strong>Sev-B</strong> (Grace: 4 hours; Schedule: 24/7).<br/>
Create <strong>Sev-C</strong> (Grace: 8 hours; Schedule: Business Hours).<br/>
Assign SLAs to departments or help topics to enforce response/resolution expectations.
</p>
<p>
  <img src="YOUR_IMAGE_LINK" height="80%" width="80%" alt="SLA Plans"/>
</p>
<br />

<!-- STEP 8: Help Topics -->

<p>
<strong>Step 8 – Configure Help Topics:</strong><br/>
Admin Panel → Manage → Help Topics → <em>Add New</em>.<br/>
Add: <strong>Business Critical Outage</strong>, <strong>Personal Computer Issues</strong>, <strong>Equipment Request</strong>, <strong>Password Reset</strong>, <strong>Other</strong>.<br/>
Help topics guide end users to categorize requests correctly and can drive routing, forms, and SLAs.
</p>
<p>
  <img src="YOUR_IMAGE_LINK" height="80%" width="80%" alt="Help Topics"/>
</p>
<br />

<!-- STEP 9: Verification -->

<p>
<strong>Step 9 – Verify Workflow:</strong><br/>
From the End-User Portal (<code>/osTicket</code>), submit a test ticket under a configured Help Topic. In the Admin/Agent Panel (<code>/scp</code>), verify the ticket appears, inherits the expected Department and SLA, can be assigned to Jane/John, updated, and closed. Confirm any notification emails (if configured).
</p>
<p>
  <img src="YOUR_IMAGE_LINK" height="80%" width="80%" alt="Verification: create and process ticket"/>
</p>
<br />

---

<h2>End Result</h2>
A production-ready osTicket configuration with clear roles, scoped departments, collaborative teams, enforced user policy, staffed agents, defined SLAs, and curated help topics—verified by a complete submit→assign→resolve ticket flow.
