# Active-Directory-Lab-Part-2

#Overview#  This project is a continuation of my Active Directory lab, focusing on integrating a client machine into a domain environment. In this phase, I configured a Windows client, joined it to the labs.local domain, and verified domain connectivity and authentication.

Tools used: VirtualBox, Windows 10 Pro, Windows Server 2022


The following sections outline my process for joining a client machine to the domain and verifying authentication and DNS functionality.

First, I installed Windows 10 Pro as the client operating system within VirtualBox and ensured it was configured on the same network adapter as the domain controller to maintain proper connectivity and a secure communication environment.

Once Windows is done installing I made sure to add my Client windows vm as a local account  do to its main function being a client of the domain <img width="1366" height="691" alt="github part 2 1" src="https://github.com/user-attachments/assets/fc705084-dc02-418c-9b98-5622f231a3ee" />
Afterward, I configured the client with an IP address within the same network as the domain controller and assigned it the same DNS server. This ensured proper connectivity, allowed for accurate name resolution, and enabled the client to successfully locate and join the domain <img width="1366" height="691" alt="github part 2 2" src="https://github.com/user-attachments/assets/37d41d54-0c5f-4de1-a3ae-9e6fac7eebe1" />
Once the client was configured on the same network, I navigated to Control Panel > System > Rename this PC (Advanced) to access system properties. From there, I initiated the domain join process. On a client or end-user device, administrative credentials are required to complete this action.  This can be accessed more quick by running the "sysdm.cpl" command in the windows seatch tab.  <img width="1366" height="691" alt="github part 2 3" src="https://github.com/user-attachments/assets/c41ec041-b999-4fbf-9ebe-2d9e6c1f00d5" />
Once the process is complete, the computer must be restarted. After rebooting, you can log in using the user credentials created on the Domain Controller Active Directory <img width="1366" height="691" alt="github part 2 4" src="https://github.com/user-attachments/assets/ce57049a-a2a3-4456-8036-ec1be62bdae8" />
After passing Authentication to verify the domain join open Command Prompt on the client device and run the whoami command. This will display the currently logged in user in the format domain\username, confirming that the client is authenticated through the domain. <img width="1366" height="691" alt="github part 2 5" src="https://github.com/user-attachments/assets/baba2593-b036-4bd7-8e8e-0e3a5656dfd8" />
After Ping The Client from the Domain Controller, and The Domain Controller from the Client. If ping to Client is not reachable go to Windows Defender firewall> Advanced Settings> inbound rules> find files and sharing services (Echo Request - ICMPv4-In), make sure this is for the domain and enable this rule so that Client is pingable.
Domain Controller Ping to Client
<img width="1024" height="768" alt="last git hub" src="https://github.com/user-attachments/assets/0f770715-c274-4ca1-9ed7-31e36f5bbc94" />
Client Ping to Domain Controller
<img width="1366" height="691" alt="last git hub 2" src="https://github.com/user-attachments/assets/545dfbae-e451-4f86-8b56-78b4ec10183b" />
Next, navigate to Active Directory Users and Computers by selecting Tools > Active Directory Users and Computers. Under the Computers container, you will see the client machine listed, confirming it has been successfully joined to the domain. In this case, the default computer name was not changed by me before joining, but the configuration is still correct.<img width="1024" height="768" alt="github part 2 6" src="https://github.com/user-attachments/assets/26d3a2b2-4634-4ec4-b292-8b015335df1e" />
#Conclusion  This project demonstrates my ability to deploy and manage a basic Active Directory environment, including configuring a domain controller, integrating a client machine, and validating domain authentication. Through this process, I gained hands-on experience with network configuration, DNS resolution, and domain services, which are essential components of enterprise IT infrastructure
