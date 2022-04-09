![image](https://user-images.githubusercontent.com/94435318/162557354-6cfe3845-74f7-45f3-a2bf-81491fbb5620.png)

# GIT Happens

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162557384-3bc40c56-8ca4-4690-a6fa-796b576c5725.png">
</p>          

Boss wanted me to create a prototype, so here it is! We even used something called "version control" that made deploying this really easy!

----------------------------------------------------------------------------------------------------------

## Click Start Machine

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162557870-fbda3f84-b801-4331-9f54-8642368faed8.png">
</p>  

## IP Address will be generated

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162557852-10d1f9e3-60b4-4ba3-bcff-0d7971141bc7.png">
</p>

### Access the Machine

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162557940-027d6e2a-7721-4fab-9b06-3ef44b64f5aa.png">
</p>

### Access openvpn

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162557995-5b4c7c4e-28d0-4221-9809-9a48a24501bc.png">
</p>

### Download the Openvpn config pack

<p align="center"> <img src="https://user-images.githubusercontent.com/94435318/162557976-db2ca54c-6454-43cb-84a3-24535bd625f8.png">
  </p>

### Start Openvpn

<p align="center"> <img src="https://user-images.githubusercontent.com/94435318/162558023-08febe3e-f445-4c58-933b-571fde3ec981.png">
  </p>

### The only task in this room is to capture the flag. Deploy the machine.

-----------------------------------------------------------------------------------------------------------

## Nmap Scan

Start gathering informationby using nmap for port scan. *Nmap tool can be used for port scanning.* 

The command I used is: nmap -sV -sC machine_IP_address

- -sV is used to service and version scan
- -sC is used to default script scan

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558117-107676ed-5517-432d-9bab-3c54abd2ef28.png">
</p>  

The scan results shows that port 80 is open under http service.
A git repository is also found in port 80 as ipaddress:80/.git

--------------------------------------------------------------------------------------------------------

## Deploy ip in Web Browser

Simply type ip address in browser. A login page appears.

![image](https://user-images.githubusercontent.com/94435318/162558265-1120b14d-b333-4dfc-b9cc-14761985628b.png)

Visit ipaddress/.git

The page shows some folders, it is an exposed git directory. We cannot check each and every folder individually.

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558427-690b24ef-a09b-4252-af96-6705a56bdc12.png">
</p>  

----------------------------------------------------------------------------------------------------------

## Gobuster 

*Gobuster is used to find the hidden directories*

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558541-4c5cda76-9432-45ab-9823-69e92ce69d93.png">
</p>  

----------------------------------------------------------------------------------------------------------

## Git Tool

*GitTools can be very helpful.*

- It contains a gitdumper.sh script which can be used to pull and copy the git repository to our local machine. 
- We can install GitTools by using the command: git clone https://github.com/internetwache/GitTools.git/

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558586-b1523847-c5a0-487c-891d-1afba9b1f261.png">
</p>  

- After successfully installing the GitTools find the path to the gitdumper.sh

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558615-10b1ccae-ec72-458e-99bf-e439ef69e9aa.png">
</p>  

*Now, use the command: ./gitdumper.sh http://MACHINE_IP_ADDRESS/.git clone*

- The command above will copy the git repository to our local system. 

- A folder named ‘clone’ will be created in the current directory in which we are.

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558663-1495033f-dae2-4d60-bb2d-414ebaa5f355.png">
</p>  

- Navigate to the clone folder.

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558781-cb62cd50-814d-49fe-92f7-38aa8567dced.png">
</p>  

- Check the status of the repository using the command git status. 

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558828-1978386b-8332-43fa-8419-8c561f85fa87.png">
</p>  

-Check if there is something in logs. Use the command git log.

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558895-592dccc8-d89b-445d-b9b7-9c3c57dd2422.png">
</p>  

*Found a commit which was made on 23rd july and which says that ‘Made the login page, boss!’.*

- Use git show commit_id command to see what was committed. Explore the code.

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558957-3996a32d-d489-4005-9eeb-e2716589a0d9.png">
</p>  

- I found the Username and password. And password is our flag.

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162558967-9883e2cd-05b1-4109-abc7-30cc58ea895e.png">
</p>

----------------------------------------------------------------------------------------------------------

## Flag Captured

<p align="center">
  <img src="https://user-images.githubusercontent.com/94435318/162559374-7a7f4f5c-edb6-4bcb-a0f7-ba181b74414a.png">
</p>

------------------------------------------------------------------------------------------------------
