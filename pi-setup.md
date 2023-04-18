# Setting up the Raspberry Pi.
## Setting up the Pi as an OLA server.
1. Install Raspbian Lite on a 32 gigabyte SD card.
2. After flashing Raspbian Lite onto the SD card connect the Pi to power and to ethernet.
3. Once you have connected it to the network connect to it via SSH.
'''
ssh pi@[YOUR-PI-IP-ADDRESS]
'''
and use the default credentials.
'''
Username: Pi
Password: raspberry
'''
4. After connecting to the Pi change the default password.
'''
sudo passwd pi
'''
5. Update the apt repository.
'''
sudo apt-get update -y
sudo apt-get upgrade -y
'''
6. After updating the Pi install OLA.
'''
sudo apt-get install ola
'''
7. After OLA finishes installing check the status of the daemon.
'''
sudo systemctl status olad
'''
8. After confirming that OLA is running visit the web portal of OLA.
'''
http://[YOUR-Pi-IP]:9000
'''
9. When you are met with the OLA homescreen click the 'Create Universe' button.
10. For the feilds type the following information.
'''
Universe ID: 1
Universe Name: MainUniverse
'''
11. Then for the input and output put the following.
'''
Input: Art-net
Output: Dummy
'''
12. After doing the above instructions click the 'save' button.
13. Reboot the Pi with the command
'''
sudo reboot
'''
OR shutdown
'''
sudo shutdown -h now
'''
