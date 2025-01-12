# Detection-Lab

# Objective

- Setting up splunk and sysmon as a detection lab
- Get some experience handling detection tools
- Get experiance building malwaree

# Tools Used

- Splunk
- Sysmon
- wireshark

  
# Skills Learned
- How to use nmap in kali
- what msfvenom can do
- Building a malware file using msfvenom
- Executing malware after being built

# Steps

- Side note if you are planning to use any new tools in your virtual machine make sure to download them while your virtual machine is connected to an NAT network or your can file share with your host computer to transfer your tool files.
- If file tranfer was used make sure the FTP (file tranfer protocol) is disabled and you host computer is completely disconnected from your VM before the malware analysis process begins otherwise you will be risking the infection of your host computer files.

  - Downloaded splunk and sysmon on my windows VM for telemetry detection
  - On my windows VM i opened RDP (remote desktop protocol) to enable connection from my kali linux VM you can find this under Settings-> Remote Desktop
    
  ![image](https://github.com/user-attachments/assets/30579720-8ad1-4bdd-8a27-d0fa73c330df)

  - Once settup i started with nmaping on my kali linux VM tofind an open port on my windows VM the command i used was: nmap -A (ip address) -Pn
    
  ![image](https://github.com/user-attachments/assets/6a43689a-6cae-434a-9ad8-c5195ceda335)

  - Results i had gotten and the open port i found is highlighted
    

  ![image](https://github.com/user-attachments/assets/45ca6dc9-f287-469d-9bbe-dede19d38a5a)

  - Im going to be useing msfvenom. My command that I used to look for payloads was: msfvenom -l payloads
  - The payload I decided to land on is in the pic below

    ![image](https://github.com/user-attachments/assets/63039cc3-9eb2-4b6e-9a05-46f924155f4e)

  - Building out my malware using msfvenom

    ![image](https://github.com/user-attachments/assets/4b643327-a99b-413e-9766-6449345d6efc)

  - File should be generated
  - Port 4444 is the default port for meterpreter
  - Make sure the file has been created using ls command
    
    
   ![image](https://github.com/user-attachments/assets/252e108d-7839-4f66-a67e-cecc223e90cf)

  - Now im going to be openning a handler to listen in on port that i want to execute on by using msfconsole command
  - Once the command is entered pressenter and you should be connected to the metaslpoit handler
  - once inside use command: use exploit/multi/handler
  - screen should look like the picture below
 
    ![image](https://github.com/user-attachments/assets/263a765d-2c9d-4b4b-b011-fd7add86ebb1)

  - If you type in options it will show u the options you currently have

    ![image](https://github.com/user-attachments/assets/2217d220-2bfd-45f7-9e0d-7af099803d9d)

  - Type in set payload and make sure to set it to the payload you want to use as you see in the picture above and the handler will change 
  - Type in set lhost (ip address) to change the lhost settings
  - Then type in the command: exploit to start listening in on our target computer. At this point we are listening in and waiting on our test maching to download our malware


  - Open up a new tab in the terminal and make sure you are in the same directory as the malware file
  - Type in the command: python3 -m http.server (port number)
 

   - This should allow our test maching to start downloading malware from our kali linux VM



    


    


  

