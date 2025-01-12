# Detection-Lab

# Objective

- Setting up splunk and sysmon as a detection lab
- Get some experience handling detection tools

# Tools Used

- Splunk
- Sysmon
- wireshark

  
# Skills Learned

# Steps

- Side note if you are planning to use any new tools in your virtual machine make sure to download them while your virtual machine is connected to an NAT network or your can file share with your host computer to transfer your tool files.
- If file tranfer was used make sure the FTP (file tranfer protocol) is disabled and you host computer is completely disconnected from your VM before the malware analysis process begins otherwise you will be risking the infection of your host computer files.

  - Downloaded splunk and sysmon on my windows VM
  - On my windows VM i opened RDP (remote desktop protocol) to enable connection from my kali linux VM you can find this under Settings-> Remote Desktop
    
  ![image](https://github.com/user-attachments/assets/30579720-8ad1-4bdd-8a27-d0fa73c330df)

  - Once settup i started with nmaping on my kali linux VM tofind an open port on my windows VM the command i used was: nmap -A (ip address) -Pn
    
  ![image](https://github.com/user-attachments/assets/6a43689a-6cae-434a-9ad8-c5195ceda335)

  - Results i had gotten and the open port i found is highlighted
    

  ![image](https://github.com/user-attachments/assets/45ca6dc9-f287-469d-9bbe-dede19d38a5a)

  - Im going to be useing msfvenom. My command that I used to look for payloads was: msfvenom -l payloads
  - The payload I decided to land on is in the pic below

    ![image](https://github.com/user-attachments/assets/63039cc3-9eb2-4b6e-9a05-46f924155f4e)

    


  

