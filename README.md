# ubuntu_desktop
ubuntu install chrome
https://medium.com/@selvamraju007/install-and-launch-ubuntu-22-04-desktop-on-google-cloud-1fba8c0f9585

Install Chrome Remote Desktop on the VM instance
The next step is to install Chrome Remote Desktop on the VM instance which you created. Download and install the Debian Linux Chrome Remote Desktop installation package:

wget https://dl.google.com/linux/direct/chrome-remote-desktop_current_amd64.deb
sudo apt-get install --assume-yes ./chrome-remote-desktop_current_amd64.deb

Setup Ubuntu desktop environment in the VM instance:
Connect your instance using SSH, refresh the repository and package lists, perform the necessary upgrade using the below commands.

sudo apt update && sudo apt upgrade

2. Install and setup display manager. Here i used SLiM for its lightweight feature

sudo apt install slim

3. Install Ubuntu desktop environment (the installation process may need around 15-20 minutes):

sudo apt install ubuntu-desktop

4. Once finishes the installation, reboot the machine.

sudo reboot

5. Once instance is back to online after the reboot, ssh the connection and start the slim using below command.

sudo service slim start


Configure the Chrome Remote Desktop service and Connect to your Ubuntu Desktop
To start the remote desktop connection, you need to have an authorization key for your Google account.

1. On your local computer, using the Chrome browser, go to the Chrome Remote Desktop command line setup page:
https://remotedesktop.google.com/headless

2. On the Set up another computer page, click Begin.

![image](https://github.com/user-attachments/assets/6c8fb3c1-e011-4eed-99e6-f1a11c133c3c)

3. Click next. You already installed the Chrome Remote Desktop on the remote computer in STEP2.

   ![image](https://github.com/user-attachments/assets/e80f800d-bd97-44de-add7-240841d2abdc)

4. Click Authorise

   ![image](https://github.com/user-attachments/assets/0260d080-2892-4cc4-9d95-3cfd98d5d2d2)

5. Now you get the command to set up and start the Chrome Remote Desktop service on your VM instance. Copy the command for Debian Linux.

   ![image](https://github.com/user-attachments/assets/3dd8e02d-159e-43fb-bbbb-00319a1376d5)

6. Copy and Paste the command to the SSH window that connects to your VM instance. Run the command.

   ![image](https://github.com/user-attachments/assets/1ecd2e88-beec-4eef-8fa0-d67fa216d375)

7. Enter a 6-digit PIN when prompted. This PIN will be used when you log into the VM instance from your Chrome.

8. On your local computer, go to the Chrome Remote Desktop web site. You will find your Ubuntu Desktop shows up in the portal.

   ![image](https://github.com/user-attachments/assets/85bb2ca8-7dec-464d-837a-0616d21bbed1)

9. Click the remote desktop instance. In this case, it is “worker-node1”. And you will be prompted to input the 6-digit PIN you set in step 7.

    ![image](https://github.com/user-attachments/assets/0bb7fecc-674a-401a-8c51-5d51b48ac04e)

10. Now you can see the ubuntu desktop and fully functional.

    ![image](https://github.com/user-attachments/assets/77efebde-3205-467d-909d-af5163a46c4e)
