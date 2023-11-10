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
To enable a more detailed analysis, I can use the -v flag to enable more verbose output. Tcpdump will attempt to perform reverse DNS lookups to resolve IP addresses to hostnames, as well as replace port numbers with commonly associated service names. I can disable this using the -n flag. By using this flag I can avoid generating additional traffic from the DNS lookups, and to speed up the analysis. <br/> I will use this command this time: "sudo tcpdump -i eth0 -vn" 
 <br/>
  <img src="https://i.imgur.com/Fyk9uJP.png" height="60%" width="60%"
  <br/>
  <br />
<br/>
Now I can see that the output now provides many more details for each packet.
 <br/>
  <img src="https://i.imgur.com/s5MomRd.png" height="50%" width="50%"
  <br/>
  <br />
<br/>
Filtering: <br/>
Tcpdump also has a feature for filtering packets. With this feature I can capture only the traffic that I really want to analyze. I'll use filtering to capture DNS traffic to a specific DNS server. I will use the command:
 <br/> "sudo tcpdump -i eth0 -vn host 8.8.8.8 and port 53 &" 
 <br/>
 <br/> This command specifies that I only want packets where the source or destination IP address matches the address 8.8.8.8 and also specifies that I only want to see packets where the source or destination port matches port 53. 
 <br/>
  <img src="https://i.imgur.com/PKBmdUK.png" height="50%" width="50%"
  <br/>
  <br />
<br/>
To list all running jobs, I will use the command: "jobs -l"
 <br/>
<img src="https://i.imgur.com/dbqJBYl.png" height="60%" width="60%"
  <br/>
  <br />
<br/>
Now, I'll note down the job ID of the above process (637). <br/> 
 Next, I will execute a "dig" command: "dig @8.8.8.8 A example.com"
 <br/>
The dig command is a utility used to query a specific DNS server (in this case 8.8.8.8), 
 <br/> 
asking it for the A record for the specified domain (in this case "example.com").
<br/>
<img src="https://i.imgur.com/gsmAEhy.png" height="60%" width="60%"
  <br/>
 <img src="https://i.imgur.com/QHDqEOR.png" height="60%" width="60%" 
  <br/>
 <br/>
 <br/>
 Once that's done, I'll use the job ID that I noted down earlier to bring the process to foreground with the following command: fg % 637
 <br/>
<img src="https://i.imgur.com/9yYQmAI.png" height="60%" width="60%"
  <br/>
  <br/>
 <br/>
We see two captured packets, as our filter rules filtered out any other traffic.
 <br/>
<img src="https://i.imgur.com/zKA6moX.png" height="60%" width="60%"
  <br/>
