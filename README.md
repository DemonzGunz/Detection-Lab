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

   ![image](https://github.com/user-attachments/assets/2c73391f-e512-4f2d-a972-70af43e1a00d)

  ![image](https://github.com/user-attachments/assets/e2060146-b549-439b-a919-ad4ee0e881a9)

  - Failed to bind to my windows VM so I will be doing some reserch
  - Used the incorrect ip address the lhost address needs to be the ip address of the host VM not the target VM

  ![image](https://github.com/user-attachments/assets/804c8a6a-24bc-4f1e-858d-679d2ac1b32a)


  - Open up a new tab in the terminal and make sure you are in the same directory as the malware file
  - Type in the command: python3 -m http.server (port number)

   ![image](https://github.com/user-attachments/assets/33d0e4f1-a132-4f86-832a-ebca60acfef4)


   - This should allow our test maching to start downloading malware from our kali linux VM
   - Open you windows VM disable real time protection under viruse and threat protection in the settings.
   - Type in the ip address for your open browser sever in your perfered browser. Then download the infected link

     ![image](https://github.com/user-attachments/assets/fe758f2c-34fd-44ff-b779-c7d4444c419a)

  - Windows protected my pc even while on an internal network

    ![image](https://github.com/user-attachments/assets/d132cde5-45f1-4109-9314-d33b2bbbe933)

  - Checking to see if there was an established connection

    ![image](https://github.com/user-attachments/assets/a87b7ab9-67d4-40f8-a736-dda0fd5d4fc4)

  - Unfortunatly it dosent show that the link has been established in the command prompt command that was used was: netstat -anob
 

  - I did find the program running in the task manager tricky little malware 


   ![image](https://github.com/user-attachments/assets/69856bd1-b361-45e3-a6f1-2485166f795e)

  - Still no luck on getting an established link to generate telemetry to spot in my Spunk program will try again another time 


     



    


    


  

