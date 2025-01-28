<p align="center">
  
![1-1](https://github.com/user-attachments/assets/899a9de9-9453-47f4-bc7c-5f0f4a96e312)

</p>

<h1>Preparing Active Directory Infrastructure in Azure</h1>
In this project, I create two virtual machines, one running Windows Server to act as a Domain Controller & DNS Server, and one running Windows 10 to act as the client. In later parts, I will deploy Active Directory, run a script that will create users in the domain that can be logged into from the client VM, manage the accounts and update group policies, simulating a real life IT environment!<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop Connection

<h2>Operating Systems Used </h2>

- Windows 10 Pro</b> (22H2)
- Windows Server</b>

<h2>Project Walk-Through:</h2>

<h3>Step 1.</h3>

![1  click create](https://github.com/user-attachments/assets/65050d87-88a2-4449-832c-524a20f5d03d)

<p>Go to resource groups in Azure and click Create</p>

<h3>Step 2.</h3>

![2  review   create](https://github.com/user-attachments/assets/7c5f795b-4ecb-4f11-a7a7-c4ec7d2c0289)

<p>Name your resource group, select your region, then click Review+Create</p>

<h3>Step 3.</h3>

![3  create](https://github.com/user-attachments/assets/4d63a03c-85f6-49c0-9c9d-ad6a1e451d03)

<p>Click create</p>

<h3>Step 4.</h3>

![4  search virtual network](https://github.com/user-attachments/assets/56c69879-2a8d-40fa-9e6d-b5617d87bb14)

<p>Search for virtual networks in Azure</p>

<h3>Step 5.</h3>

![5  click create](https://github.com/user-attachments/assets/d48a5931-2492-4ec6-bdee-b6d008f97255)

<p>Click create virtual network</p>

<h3>Step 6.</h3>

![6  review   create vnet](https://github.com/user-attachments/assets/99d68892-f8b3-4643-bc2b-d0fbe25a4d8e)

<p>Select the resource group you created, name the Virtual Network, select the region, then click Review + create</p>

<h3>Step 7.</h3>

![7  click create](https://github.com/user-attachments/assets/b543731b-65eb-4198-ae2b-32d1777b3653)

<p>Click create</p>

<h3>Step 8.</h3>

![8  VNet deployed](https://github.com/user-attachments/assets/5cdc118f-6ea4-46a1-ae25-cf0d5d292f12)

<p>The virtual network has sucessfully been deployed.</p>

<h3>Step 9.</h3>

![9  search virtual machines](https://github.com/user-attachments/assets/2d64a2d6-448d-4276-86b2-78e28f5cd61d)

<p>Search and select virtual machines in Azure</p>

<h3>Step 10.</h3>

![10  click create vm](https://github.com/user-attachments/assets/dd7809b7-35cf-4eeb-a408-a14afd6a5c5f)

<p>Click create Azure virtual machine</p>

<h3>Step 11.</h3>

![11  dc settings](https://github.com/user-attachments/assets/902ca6d0-b2aa-4391-958b-024bcb20e4c9)

<p>Select the resource group you created, name the virtual machine, select the region, choose Windows Server 2022 as the image, use a size of 2 vcpus, 8GiB memory. This vm will serve as our domain controller.</p>

<h3>Step 12.</h3>

![12  dc user pass](https://github.com/user-attachments/assets/0a781c85-f739-40d6-9b32-7dcc262fba58)

<p>Create a username and password for this vm, then click Next: Disks ></p>

<h3>Step 13.</h3>

![13  click next networking](https://github.com/user-attachments/assets/6ea97c5b-e7d1-49e4-87d2-c5d8352879a6)

<p>Click Next : Networking ></p>

<h3>Step 14.</h3>

![14  dc setup network](https://github.com/user-attachments/assets/7e568bd3-22e5-43e9-8ede-cfade4359fba)

<p>Select the virtual network you created, choose the default subnet, then click Review + create</p>

<h3>Step 15.</h3>

![15  click create](https://github.com/user-attachments/assets/f137d64d-c637-4667-85ad-e8f4d4296e34)

<p>Click create</p>

<h3>Step 16.</h3>

![16  dc deployed](https://github.com/user-attachments/assets/2fb5b95b-2f5d-4d7a-bc94-36edf22085f6)

<p>The virtual machine Windows server that will act as our domain controller has now been deployed</p>

<h3>Step 17.</h3>

![17  create another vm](https://github.com/user-attachments/assets/65df551b-b50a-4014-8ed3-f79e7d128c75)

<p>Search virtual machines again and click create to make another one</p>

<h3>Step 18.</h3>

![18  client setup](https://github.com/user-attachments/assets/a0b26a99-d8a5-4642-b4dd-ccdb9c560610)

<p>Select the resource group that was created, name the virtual machine, select the region, select Windows 10 Pro 22H2 as the image, select a size of 2vcpus and 8GiB memory. This virtual machine will serve as our client that we will later add to the domain controller</p>

<h3>Step 19.</h3>

![19  client user   pass](https://github.com/user-attachments/assets/05cd23fb-a87c-4991-b51a-a6ec9321a5b3)

<p>Create a username and password for the client vm, check the box, then click Next : Disks ></p>

<h3>Step 20.</h3>

![20  next networking](https://github.com/user-attachments/assets/850e9220-e792-4376-9e5a-3f3dfe6fe46e)

<p>Click Next : Networking ></p>

<h3>Step 21.</h3>

![21  review   create](https://github.com/user-attachments/assets/1c8b1492-d755-485b-a048-1dc8683ee98f)

<p>Select the virtual network we created earlier, select the default subnet, then click Review + create</p>

<h3>Step 22.</h3>

![22  click create](https://github.com/user-attachments/assets/14b57468-5c21-4d0e-b064-11c7e427a20c)

<p>Click create</p>

<h3>Step 23.</h3>

![23  client deployed](https://github.com/user-attachments/assets/9d03f149-3212-4e88-a859-0f28f7760d6c)

<p>The virtual machine serving as our client has now been deployed</p>

<h3>Step 24.</h3>

![24  dc-1 network settings](https://github.com/user-attachments/assets/c1605581-5b95-44e1-8512-ee3b34d12bd2)

<p>Go to the domain controller vm, go under networking, and click network settings</p>

<h3>Step 25.</h3>

![25  click NIC](https://github.com/user-attachments/assets/9f7ce47d-a63e-475e-9109-4afbbc9aec6d)

<p>Click on the Network Interface Card</p>

<h3>Step 26.</h3>

![26  click ipconfig](https://github.com/user-attachments/assets/46f0a17e-503c-48df-b362-842e22a164cb)

<p>Click on ipconfig1</p>

<h3>Step 27.</h3>

![27  change to static](https://github.com/user-attachments/assets/b8bc44bd-7686-4eb5-b331-f139bdd126ce)

<p>Change the private IP address to "static" then click save</p>

<h3>Step 28.</h3>

![28  private ip updated](https://github.com/user-attachments/assets/e4de78c8-bd08-411f-b973-3b57ed25b879)

<p>The private IP address should now be static. This ensures the private IP will never change, preventing any connectivity issues from the client vm to the domain controller vm in the future.</p>

<h3>Step 29.</h3>

![29  get dc-1 public ip](https://github.com/user-attachments/assets/e233878d-9c76-4c81-9467-0717bccf6cd1)

<p>Go back to networking of the domain controller, then grab the public IP address</p>

<h3>Step 30.</h3>

![30  connect with rdc](https://github.com/user-attachments/assets/fc24b34c-d64d-4fa7-a172-7416a68e2ab3)

<p>Enter the public IP into Remote Desktop Connection, then click Connect</p>

<h3>Step 31.</h3>

![31  enter dc credentials](https://github.com/user-attachments/assets/f64dc190-6561-4af2-bf73-7e9a5147a9a5)

<p>Enter the credentials for the domain controller vm, then click OK</p>

<h3>Step 32.</h3>

![32  go to windows firewall](https://github.com/user-attachments/assets/02a7c881-a937-4664-a8d7-8e50932194d1)

<p>Once your inside the domain controller vm, type "wf.msc" into the windows search bar and click it</p>

<h3>Step 33.</h3>

![33  disable firewall](https://github.com/user-attachments/assets/4d46171a-0778-4199-8409-b1a1c27aca44)

<p>This will take you to Windows Firewall. Click "Windows Defender Firewall Properties" then set the Firewall state to "Off" for Domain profile, Private profile, and Public profile. Then click Apply and OK. This is for intended lab purposes only</p>

<h3>Step 34.</h3>

![34  disabled](https://github.com/user-attachments/assets/24c67c59-d079-495d-a674-1e30bd24ddf0)

<p>The firewall should now be disbaled for all profiles</p>

<h3>Step 35.</h3>

![35  get dc-1 private ip](https://github.com/user-attachments/assets/262d0a94-d7cf-473a-9d0a-8b46740e3b28)

<p>Go back to Azure, go to the domain controller vm, go to Networking, then grab the private IP address</p>

<h3>Step 36.</h3>

![36  go to client-1 network settings](https://github.com/user-attachments/assets/f2dcbc89-eee4-45ce-be6b-cdba83db510f)

<p>Now go to the client vm, Networking, and click network settings</p>

<h3>Step 37.</h3>

![37  go to client-1 NIC](https://github.com/user-attachments/assets/2dc4ba8f-f0f0-4b5e-9ceb-14746042b658)

<p>Click the Network Interface Card</p>

<h3>Step 38.</h3>

![38  enter private ip](https://github.com/user-attachments/assets/8b7c8349-9859-4f2b-88f7-7c97c6cbe0c0)

<p>Click DNS servers, select Custom, and enter the private IP address of the domain controller vm. This will set the domain controller vm as the DNS server for the client vm.</p>

<h3>Step 39.</h3>

![39  restart client-1](https://github.com/user-attachments/assets/a7acfbc6-e5c5-4381-8116-31b732b2d5b4)

<p>Now go back to your virtual machines, select the client vm, click restart, then click Yes. This will apply the changes.</p>

<h3>Step 40.</h3>

![40  get client-1 public ip](https://github.com/user-attachments/assets/796140b3-c306-4762-8cd1-7ac306da3966)

<p>Now go to the client vm's networking tab and grab the public IP address</p>

<h3>Step 41.</h3>

![41  enter ip into rdc](https://github.com/user-attachments/assets/5c312b50-548a-4446-be73-469eec98ab99)

<p>Open remote desktop, enter the public IP of the client vm, then click Connect</p>

<h3>Step 42.</h3>

![42  enter client-1 credentials](https://github.com/user-attachments/assets/4d92c105-f699-4946-83bf-1fa2073f6787)

<p>Enter the credentials of the client vm, then click OK</p>

<h3>Step 43.</h3>

![43  open up powershell](https://github.com/user-attachments/assets/2c6b904f-c1aa-4d31-a5aa-891d3a4fff84)

<p>Once inside the client vm, type and open Windows Powershell</p>

<h3>Step 44.</h3>

![44  ping dc-1](https://github.com/user-attachments/assets/f754e146-63d6-4250-823e-b616dc45cbb3)

<p>Ping the private IP address of the domain controller vm using the "ping" command to test connectivity</p>

<h3>Step 45.</h3>

![45  ping success](https://github.com/user-attachments/assets/81de23ad-3413-47f6-b0df-540282513331)

<p>If every step was done right, the ping should have been successful</p>

<h3>Step 46.</h3>

![46  run ipconfig](https://github.com/user-attachments/assets/dde672ae-df96-4b3b-a124-1359b5864aad)

<p>Now run the ipconfig /all command</p>

<h3>Step 47.</h3>

![47  DNS IP success](https://github.com/user-attachments/assets/c01cba43-a97b-4e3a-b9c1-a774b2796caa)

<p>This should show that the domain controller vm is successfully serving as a DNS server to the client vm by using its private IP address</p>

<h2>Active Directory Infrastructure Has Been Prepared!</h2>

<p>In this part, we have successfully created two virtual machines, one running Windows Server to act as a Domain Controller & DNS Server, and one running Windows 10 to act as the client. In later parts, we will deploy Active Directory, run a script that will create users in the domain that can be logged into from the client VM, manage the accounts and update group policies, simulating a real life IT environment!</p>





























