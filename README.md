# Packet Capture Practice with tcpdump

# Description
 - In this lab I will demonstrate how to access and manage group policies using the Group Policy Management Tool. This application allows you to set policies that will manage the way machines in your domain behave. You can apply these policies to the whole domain or to separate Organizational Units (OUs). In this instance, I want to add a new policy regarding the Desktop Wallpaper, to the Developers OU that I created in the virtual domain.
   
# Enviornments & Utilities Used
 - Tcpdump
 - Linux Virtual Machine

# Walkthrough
<p align="center">
Step 1: <br/> Launch Group Policy Management Application 
  <br/>
  <img src="https://i.imgur.com/AxJSw8l.jpg" height="25%" width="30%"
<br/>
  <br />
  <br/>
  Step 2:
  <br /> 
  I’ll expand the tree until I’ve reached the example domain tree and find the Developers OU inside it. To create a new policy, right click on the Developer option and select the first menu entry: Create a GPO in this domain and Link it here.<br/>
  <img src="https://i.imgur.com/098Na3c.jpg" height="70%" width="70%"
<br />
<br />
<br/>
Step 3:
<br/>
 When you click this option, you will be prompted to set a name for the policy and once you do, the policy will get added to the OU.<br/>
  <img src="https://i.imgur.com/gVgFNuL.jpg" height="60%" width="60%"
  <br/>
  <br />
<br/>
Step 4:
<br/>
I want to set a default wallpaper for the machines in the Developers OU, so we will call our policy "New Wallpaper". Once created, I want to edit the policy. To do this, right-click on the entry and click on the first menu entry “Edit".
 <br/>
  <img src="https://i.imgur.com/clHscZw.jpg" height="80%" width="80%"
  <br/>
  <br />
<br/>
Step 5:
<br/>
Since I want to set the wallpaper, I need to navigate to this setting by going to: <br/> 
[User Configuration > Policies > Administrative Templates > Desktop > Desktop] <br/>
This will open a list of possible settings that I can configure, including the Desktop Wallpaper. <br/> To set the wallpaper, double-click on the "Desktop Wallpaper" entry.
 <br/>
  <img src="https://i.imgur.com/f2PcdIh.jpg" height="80%" width="80%"
  <br/>
  <br />
<br/>
Step 6:
<br/>
The window that opens allows you to set the wallpaper. <br/> Click on the “Enabled” button and then enter the file path for the wallpaper.
 <br/>
<img src="https://i.imgur.com/XgBinZL.jpg" height="50%" width="50%"
  <br/>
  <br />
<br/>
Step 7:
<br/>
Once I click OK, the group policy is created! To verify this, <br/> I can go back to the Group Policy Management application and click the Settings tab of the new policy and verify the changes were made.
 <br/>
<img src="https://i.imgur.com/LdqduXS.jpg" height="80%" width="80%"
  <br/>
 <br/>
