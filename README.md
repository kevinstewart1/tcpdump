# Packet Capture Practice with tcpdump

# Description
 - In this lab I will demonstrate how to access and manage group policies using the Group Policy Management Tool. This application allows you to set policies that will manage the way machines in your domain behave. You can apply these policies to the whole domain or to separate Organizational Units (OUs). In this instance, I want to add a new policy regarding the Desktop Wallpaper, to the Developers OU that I created in the virtual domain.
   
# Enviornments & Utilities Used
 - Tcpdump
 - Linux Virtual Machine

# Walkthrough
<p align="center">
Let's Start! <br/> To use tcpdump to start listening for any packets on the interface, I'll enter the command "sudo tcpdump -i eth0"
  <br/>
  <img src="https://i.imgur.com/mgbNLIR.png" height="50%" width="50%"
<br/>
  <br />
  <br/>
This will output some basic information about packets it sees. It'll continue to do this until we tell it to stop. <br/> Using Ctrl+C will stop the stream. You can see that once tcpdump stops, it prints a summary of the capture performed, showing the number of packets captured, filtered, or dropped. <br/>
  <img src="https://i.imgur.com/tTqSqpH.png" height="70%" width="70%"
<br />
<br />
<br/>
<br/>
To enable a more detailed analysis, I can use the -v flag to enable more verbose output. Tcpdump will attempt to perform reverse DNS lookups to resolve IP addresses to hostnames, as well as replace port numbers with commonly associated service names. I can disable this using the -n flag. By using this flag I can avoid generating additional traffic from the DNS lookups, and to speed up the analysis. <br/> I will use this command this time: "sudo tcpdump -i eth0 -vn" 
 <br/>
  <img src="https://i.imgur.com/Fyk9uJP.png" height="60%" width="60%"
  <br/>
  <br />
<br/>
<br/>
Now I can see that the output now provides many more details for each packet.
 <br/>
  <img src="https://i.imgur.com/s5MomRd.png" height="80%" width="80%"
  <br/>
  <br />
<br/>
Filtering: <br/>
Tcpdump also has a feature for filtering packets, so I can capture only the traffic that I really want to analyze. I'll use filtering to only capture DNS traffic to a specific DNS server. 
 <br/> I will use the command "sudo tcpdump -i eth0 -vn host 8.8.8.8 and port 53 &". 
 <br/> This command specifies that I only want packets where the source or destination IP address matches the address 8.8.8.8 and also specifies that I only want to see packets where the source or destination port matches port 53. 
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
