<h1>Creating Virtual Machines via Hyper-V Manager</h1>



<h2>Description</h2>

<p>A Virtual Machine (VM) is a software-based computer that runs an operating system and applications just like a physical computer, but it exists entirely in a virtualized environment.</p>

<p>Steps to create the Virtual Server:</p>
1. Log-in to your computer, search for Hyper-V Manager, and open it.<br>
2. On the Actions, select the Virtual Switch Manager.<br>
3. On the Virtual Switch Manager (left side of the window), highlight “New virtual network switch” and then highlight “External” type (on the right side).<br>
4. Select the Create Virtual Switch button. Name your switch as External.<br>
5. Under Connection Type, select External network: and select your outside network. On my lab, I am using the LAN connection.<br>
6. Select Apply and Yes on the warning.<br>
7. On the Virtual Switch Manager (left side of the window), highlight “New virtual network switch” and then highlight “Internal” type (on the right side).<br>
8. Select the Create Virtual Switch button. Name your switch as Internal.<br>
9. Under Connection Type, select Internal network and select Apply. Select OK.<br>
10. At the Hyper-V Manager window, go to the right side (under Actions) and select New > Virtual Machine.<br>
11. On the New Virtual Machine Wizard, at the Before You Begin, select Next.<br>
12. On the Specify Name and Location, Because I would like to store the Lab VM on an external Hard Drive, I am checking the option named Store the virtual machine in a different location. Name your server for easy identification: WinServerLab, then select Next.<br>
13. On the Specify Generation, select Generation 2 (this is because I am supporting 64-bit OS), then click on Next.<br>
14. On the Assign Memory, use the recommended Startup memory: 4096 MB, then Next.<br>
15. On the Configure Networking, dropdown to “External”, then Next.<br>
16. On the Connect Virtual Hard Disk, leave the default values under the Create a virtual disk (on my Lab, it’s an External HDD), then select Next.<br>
17. On the Installation Options, select the Install an operating system from bootable CD/DVD-ROM option, then select the Image file (.iso): option. Browse to where you save your .ISO, then select Next.<br>
18. At the Completing the New Virtual Machine Wizard, select Finish.<br>
19. Right-click on your Virtual Machine and select Settings.<br>
20. Highlight “Add Hardware” and highlight Network Adapter, then Add.<br>
21. Under Virtual switch:, select the dropdown option named “Internal”.<br>
22. To load the OS, right-click on your Virtual Machine and select Connect.<br>
23. Your Virtual Machine window opens up. Select Start and immediately press any key to install your .ISO file. Note: if you didn’t, just select the “Reset” icon and click any key.<br>
24. At the Microsoft Server Operating System Setup, select Next with the default preferences.<br>
25. Click Install now; highlight the Windows Server 2022 Standard Evaluation (Desktop Experience) and select Next. Note: the option without Desktop are not for GUIs, just command lines).<br>
26. Accept the Terms and Next.<br>
27. Select Custom: Install Microsoft Server Operating System only (advanced).<br>
28. Ensure Drive 0 Unallocated Space is selected and select Next. Take a BREAK!!!<br>
29. The installation will take approximately 15 mins.<br>
30. Customize settings will ask you to create a password. Note: for this Lab, I am selecting Password1!. Select Finish.<br>
31. When prompt, click Connect (for Lab purposes, I am keeping the default Display configuration). Your username is Administrator with your selected password.<br>
32. Minimize Server Manager.<br>
33. On the search bar, type CMD.<br>
34. On the Command Prompt, ping google.com. Note: If pings are successful, let’s identify your Network Adapters.<br>
35. On the search bar, type Network Connections. The Network Connections window should have two adapters. Right click the first one and select Status. We are looking at the “IPv4 Connectivity:” line. On the one with Internet access, close the status, right click and rename it to ExternalNetwork. The adapter with “No Internet access”, close the status and rename as InternalNetwork.<br>
36. Right click on the InternalNetwork, select Properties, then double-click on Internet Protocol Version 4 (TCP/IPv4).<br>
37. When the new window opens, select Use the following IP address: 172.16.0.1, Subnet mask: 255.255.255.0, Default gateway: leave it empty.<br>
38. Under the “Use the following DNS server:”, under “Preferred DNS server:” type 172.16.0.1 and OK twice.<br>
39. Next, rename your PC. Right-click on the Start button and select System.<br>
40. At the Settings window, select “Rename this PC”, rename it to DC, and click Next.<br>
41. Click “Restart Now” and Continue. Your VM will restart.


<br />


<h2>Utilities Used</h2>

- <b>Hyper-V Manager</b> 

<h2>Environments Used </h2>

- <b>Windows 11</b> (24H2)

<h2>Program walk-through:</h2>

<p align="center">
Server Lab Settings: <br/>
<img src="https://i.imgur.com/ebEwalm.png" height="80%" width="80%""/>
<br />
<br />
Client Lab Settings:  <br/>
<img src="https://i.imgur.com/N5sgVY6.png" height="80%" width="80%""/>
<br />

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
