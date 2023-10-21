<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (ISS)
- osTicket

<h2>Operating Systems Used </h2>

- Windows 10</b> (22HS)</li>

<h2>Post-Install Configuration Objectives</h2>
<ol>
  <li>Familiarity with the UI of osTicket</li>
  <li>Creating and Configuring Roles</li>
  <li>Creation of Tickets</li>
  <li>Creating Agents and Users</li>
  <li>Setting up Service Level Agreements (SLA Plans) in ticketing system</li>
  <li>Configuring Help Topics</li>
</ol>

<h2>Configuration Steps</h2>

<!-- <img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/> -->

<h3>Configuring Roles, Departments, & Teams</h3>

<p>
  
<ul>
  <li><b>Note</b>: There are two panels when navigating osTicket; <b>Agent Panel</b> and <b>Admin Panel</b>, you'll know which panel you are on if the <b>opposite panel</b> is displayed on the top right of the UI next to your user login name</li>
  <ul>
    <li>In this example, the user "Landon" is on the Agent Panel</li>
</br>
    <img width="800" alt="Admin : User Example" src="https://github.com/landonbmartin/post-install-config/assets/148168629/7e506eb0-16df-47b4-945a-002060c9afe7">
  </ul>
</br>
  <li><b>Roles</b> grant certain permisions to Agents in an Department they are assigned to</li>
  <ul>
    <li>In the <b>Admin Panel</b>, go to the <b>Agents</b> tab and click on <b>Roles</b>, then click on <b>Add New Role</b></li>
    <ul>
      <li><b>Note</b>: osTickets creates four Roles (All Access, Expanded Access, Limited Access, and View Only) by default.</li>
</br>
<img width="800" alt="Agents - Roles Interface" src="https://github.com/landonbmartin/post-install-config/assets/148168629/2121f439-0b44-45ea-a144-a1efc22b697e">
    </ul>
</br>
    <li>Name the new Role <b>Supreme Admin</b>, and click on the <b>Permissions</b> tab; in this tab you can assign specific permissions to this role. For our "Supreme Admin" Role, we will check every box under the <b>Tickets</b>, <b>Tasks</b>, and <b>Knowledgebase</b> tabs. Click on <b>Add Role</b> to finish and create the role.</li>
    <ul>
</br>
      <img width="800" alt="Supreme Admin Permissions" src="https://github.com/landonbmartin/post-install-config/assets/148168629/db1711bb-c880-421d-bafe-1a26a589588c">
    </ul>
</br>
  </ul>

  <li><b>Departments</b> are needed to route and resolve tickets based on their importance or instructions</li>
  <ul>
  <li>Still on the Agents tab, click on <b>Departments</b> and click on <b>Add New Department</b></li>
  <ul>
    <li><b>Note</b>: Much like Roles, osTicket also creates two Departments (Maintenance and Support) by default</li>
</br>
    <img width="800" alt="Add New Department" src="https://github.com/landonbmartin/post-install-config/assets/148168629/c1cd9be2-c819-4c5b-b0f9-1e3124383488">
  </ul>
</br>
  <li>Name the Department <b>System Administrators</b> (we'll leave everything else by default for now), then click on <b>Create Dept</b> to create Department</li>
  <ul>
</br>
    <img width="700" alt="Create System Administrator" src="https://github.com/landonbmartin/post-install-config/assets/148168629/e1a0e6e3-01ea-4d4b-89e7-9625da80fda7">
  </ul>
</br>
  </ul>

  <li><b>Teams</b> allow us to organize Agents from different Departments in osTicket to handle specific issues and supersede Agents and their Departments' parameter rules</li>
  <ul>
    <li>In the Agents tab, click on <b>Teams</b> and click on <b>Add New Team</b></li>
    <ul>
    <li><b>Note</b>: Just like previous set ups, osTicket creates a Team (Level I Support) by default</li>
</br>
    <img width="800" alt="Add New Teams" src="https://github.com/landonbmartin/post-install-config/assets/148168629/a556444c-73ef-4600-bb11-83330d2fd38a">
    </ul>
</br>
    <li>Name the Team <b>Level II Support</b> then click on <b>Create Team</b> to create the Team</li>
    <ul>
</br>
      <img width="800" alt="Teams Level II Support" src="https://github.com/landonbmartin/post-install-config/assets/148168629/2b637eba-411b-411b-b886-d4295357d9d5">
    </ul>
</br>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Allowing anyone to create Tickets</h3>

<p>
  
<ul>
  <li>In the <b>Admin Panel</b>, head to the <b>Settings</b> tab and click on <b>Users</b>, make sure <b>Registration Required</b> is unchecked. This will allow us to create tickets anonymously</li>
  <ul>
</br>
    <img width="800" alt="User Settings - Generate Tickets" src="https://github.com/landonbmartin/post-install-config/assets/148168629/4f96eb88-7fcd-4cff-9b72-41a9cf3eea81">
  </ul>
</br>
</ul>
  
</p>

</br>

<h3>Adding Agents and Users</h3>

<p>
  
<ul>
  <li><b>Agents</b> (or Workers) are given the access to the help desk in osTicket to respond, resolve, and update the status of tickets</li>
  
  <ul>
    <li>In the <b>Admin Panel</b>, head to the <b>Agents</b> tab and click on <b>Add New Agent</b></li>
    <ul>
</br>
      <img width="800" alt="Add New Agents" src="https://github.com/landonbmartin/post-install-config/assets/148168629/7eb4171d-a931-4128-ac8e-b352fbe99525">
    </ul>
</br>
    <li>For this tutorial, we will be creating two new Agents <b>Jane</b> and <b>John</b>, it is advise to have a notepad ready to catalog login information as you enter their credentials, but we will set their user names as <b>[name].doe</b> and both of their passwords as <b>Password1</b> for convenience (which is our admin password from the installation tutorial)</li>
    <ul>
      <li>Fill in the Agent's basic info and set the Agent's email address as <b>[name].doe@osticket.com</b> and click on <b>Set Password</b></li>
</br>     
      <img width="800" alt="Adding Agent - Jane" src="https://github.com/landonbmartin/post-install-config/assets/148168629/cf7bb25c-1725-4297-8fad-b05e81af93d8">
      </ul>
</br>
      <li>Set the Agent's password to <b>Password1</b> and unchecked the boxes to prevent the Agent for our example from needing to reset password or change password after login</li>
</br> 
      <img width="600" alt="Password Set - Jane" src="https://github.com/landonbmartin/post-install-config/assets/148168629/be429faa-53cd-4ca5-b781-f46c15f030e2">
    </ul>
</br> 
    <li>Go the <b>Access</b> tab to set the Agent's <b>Primary Department</b> (Mandatory to create the Agent). <b>Extended Access</b> can also be added to the Agent in order to access additional Departments</li>
    <ul>
</br>
    <img width="800" alt="Selecting Access - Jane" src="https://github.com/landonbmartin/post-install-config/assets/148168629/9fa89bd5-8cb6-4933-96ac-1b8d7be1eee6">
    </ul>
</br>
    <li>OPTIONAL: Head to the <b>Teams</b> tab to assign the Agent to a Team</li>
  </ul>
  
  <li><b>Users</b> (or Customers) are creators and owners of tickets and by using osTicket they are able to track the status of their tickets</li>
  
  <ul>
    <li>In the <b>Agent Panel</b>, go to the <b>Users</b> tab and click on <b>Add User</b></li>
    <ul>
</br>
      <img width="800" alt="Add New Users" src="https://github.com/landonbmartin/post-install-config/assets/148168629/afc883a8-edee-4ec2-b745-d32ea4d66a6e">
    </ul>
</br>
    <li>For this tutorial, we will be creating two new Users <b>Ken</b> and <b>Karen</b> and setting up usernames, emails, and passwords similar to our Agents.</li>
    <ul>
</br>
      <img width="600" alt="Create User - Karen" src="https://github.com/landonbmartin/post-install-config/assets/148168629/549e9003-2a75-449f-9086-5f6e5dbef1c8">
    </ul>
</br>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Adding SLA Plans</h3>

<p>
  
<ul>
  <li><b>Service Level Agreements</b> or SLA Plans provide a length of time for the ticket Administrator when the ticket is expected be CLOSED. They can also be designated to specific Departments or Help Topics</li>
  <li>In the <b>Admin Panel</b>, go to the <b>Manage</b> tab and drop down to <b>SLA</b> then click on <b>Add New SLA Plan</b></li>
  <ul>
</br>
    <img width="800" alt="Manage SLA" src="https://github.com/landonbmartin/post-install-config/assets/148168629/4e91d24f-5a2c-4365-91ce-abcf9eb74c9e">
  </ul>
</br>
  <li>osTicket by default has the SLA Plan <b>Default SLA</b>. We will be creating three SLA Plans each with their own length of time for different kinds of importance of the ticket, from highest priority to lowest priority:</li>
  <ol>
    <li>SEV-A with <b>1 hour Grace Period, 24/7 Schedule</b>, suitable for tickets that are business critical</li>
    <li>SEV-B with <b>4 hour Grace Period, 24/7 Schedule</b>, suitable for tickets affecting employees such as troubleshooting or PC problems</li>
    <li>SEV-C with <b>8 hour Grace Period, business hours Schedule</b>, suitable for tickets requesting new equipment</li>
  </ol>
  <li>Example of creating SEV-A SLA Plan, click on <b>Add Plan</b> to create the SLA Plan</li>
  <ul>
</br>
    <img width="800" alt="SEV-A SLA" src="https://github.com/landonbmartin/post-install-config/assets/148168629/853106f8-1ca3-420f-baaa-23c349c9956b">
  </ul>
</br>
</ul>
  
</p>

</br>

<h3>Configuring Help Topics</h3>

<p>
  
<ul>
  <li><b>Help Topics</b> are helpful to streamline the ticket entry experience for the user by helping them specify their ticket info and also determine what Department the ticket should go to</li>
  <li>In the <b>Admin Panel</b>, go to the <b>Manage</b> tab and click on <b>Add New Help Topic</b></li>
  <ul>
    <li><b>Note</b>: osTicket creates four Help Topics (Feedback, General Inquiry, Report a Problem, and Report a Problem / Access Issue) by default</li>
</br>
    <img width="800" alt="Add New Help Topics" src="https://github.com/landonbmartin/post-install-config/assets/148168629/cbc9e7e5-2372-45a6-9661-b7544de2eba8">
  </ul>
</br>
  <li>We will create four different Help Topics based on the potential serverity a ticket could have, from highest to lowest priority:</li>
  <ol>
    <li>Business Critical Outage</li>
    <li>Personal Computer Issues </li>
    <li>Equipment Request</li>
    <li>Password Reset</li>
  </ol>
  <li>Example of entering credentials for the Help Topic "Password Reset," click on <b>Add Topic</b> to create the Help Topic</li>
  <ul>
</br>
    <img width="800" alt="Help Topic - Password Reset" src="https://github.com/landonbmartin/post-install-config/assets/148168629/17ce7c54-1911-4bba-ae59-afee4c7e8b63">
  </ul>
</br>
  
</ul>
  
</p>

</br>

<h3>Further Reading and Manual</h3>
<ul>
  <li>This concludes to basics of osTicket configuration, but further information and research on the features of osTicket can be found in the official online doccumentation <a href= "https://docs.osticket.com/en/latest/index.html">here</a></li>
</ul>

<br />

<h3 align = "right">Next Tutorial - <a href="https://github.com/landonbmartin/ticket-lifecycle">osTicket - Ticket Lifecycle</a></h3>
