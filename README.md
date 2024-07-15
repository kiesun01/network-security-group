![image](https://github.com/user-attachments/assets/5844bd96-1969-45d9-aabd-1bdd93712e47)
</p>

<h1>Azure Network Security Groups(NSGs)</h1>
Tutorial for Network Security Groups<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Users and Computers

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Active Subscription (Creation of Reasearch Group, VMs, Virtual Networks, Subnets)
- Active Directory running in Azure on a virtual machine (DC1)
- Client machine running in Azure on a VM (Client1) and joined to the domain
- Folders/Groups created in "Sharing Resources Over The Network With Permissions"

<h2>Steps: 1 - 7</h2>

![image](https://github.com/user-attachments/assets/ecb61edd-d4a5-46a9-aad1-e5c67c2ba559)
<p>
Step 1: Log into DC1 -> Active Directory Users and Computers -> mydomain.com -> New -> Organizational Unit -> Name: _SECURITY_GROUPS
</p>
<br />

![image](https://github.com/user-attachments/assets/8887f659-86ad-4d2f-9c9c-579933b27635)
<p>
Step 2: _SECURITY_GROUPS -> New -> Group -> Group Name: ACCOUNTANTS, Group Type: Security -> Ok
</p>
<br />

![image](https://github.com/user-attachments/assets/c15ee935-76a8-45c5-9ac1-7007d628255f)
<p>
Step 3: ThisPC -> Windows(C:) -> accounting -> Properties -> Sharing -> Share -> add ACCOUNTANTS -> Permission Level: Read/Write -> Share
</p>
<br />

![image](https://github.com/user-attachments/assets/cd669a42-4ed8-4e81-b5a1-53e19ca82d1d)
<p>
Step 4: Log into Client1 -> Attempt to access accounting folder from generic user(ex:cutoco.kupe) who is NOT in the ACCOUNTING group
</p>
<br />

![image](https://github.com/user-attachments/assets/9416a23f-2e92-4c89-918a-f1af22fa7b70)
<p>
Step 5: Log into DC1 -> Active Directory Users and Computers -> _SECURITY_GROUPS -> ACCOUNTANTS -> Members -> Add... -> Enter username(ex:cutoco.kupe) -> Check Names -> Ok -> Apply -> Ok
</p>
<br />

![image](https://github.com/user-attachments/assets/2c86cbc2-5291-404f-b28b-6004b0549822)
<p>
Step 6: Log out of Client1(to refresh new permissions) -> Log back in as user(ex: bes.jom)
</p>
<br />

![image](https://github.com/user-attachments/assets/7b060198-5402-4fbc-a5c6-03d1dc623bb2)
<p>
Step 7: Navigate to \\dc1 -> attempt to open accounting folder -> success!
</p>
<br />
