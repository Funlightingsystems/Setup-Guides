# Setting up the Raspberry Pi.
## Setting up the Pi as an OLA server.
1. Install Raspbian Lite on a 32 gigabyte SD card.
2. After flashing Raspbian Lite onto the SD card connect the Pi to power and to ethernet.
3. Once you have connected it to the network connect to it via SSH.
```
ssh pi@[YOUR-PI-IP-ADDRESS]
```
and use the default credentials.
```
Username: Pi
Password: raspberry
```
4. After connecting to the Pi change the default password.
```
sudo passwd pi
```
5. Update the apt repository.
```
sudo apt-get update -y
sudo apt-get upgrade -y
```
6. After updating the Pi install OLA.
```
sudo apt-get install ola
```
7. After OLA finishes installing check the status of the daemon.
```
sudo systemctl status olad
```
8. After confirming that OLA is running visit the web portal of OLA.
```
http://[YOUR-Pi-IP]:9000
```
9. When you are met with the OLA homescreen click the 'Create Universe' button.
10. For the feilds type the following information.
```
Universe ID: 1
Universe Name: MainUniverse
```
11. Then for the input and output put the following.
```
Input: Art-net
Output: Dummy
```
12. After doing the above instructions click the 'save' button.
13. Reboot the Pi with the command
```
sudo reboot
```
OR shutdown
```
sudo shutdown -h now
```

## Setting up the Pi as a lighting client
1. Install Raspbian Lite on a 32 gigabyte SD card.
2. After flashing Raspbian Lite onto the SD card connect the Pi to power and to ethernet.
3. Once you have connected it to the network connect to it via SSH.
```
ssh pi@[YOUR-PI-IP-ADDRESS]
```
and use the default credentials.
```
Username: Pi
Password: raspberry
```
4. After connecting to the Pi change the default password.
```
sudo passwd pi
```
5. Update the apt repository.
```
sudo apt-get update -y
sudo apt-get upgrade -y
```
6. After updating the apt respository type the command below to install git.
```
sudo apt-get install git -y
```
7. After git installs clone the 'python-lights' repo.
```
sudo git clone http://github.com/Funlightingsystems/python-lights
```
8. Enter the python-lights directory.
```
cd python-lights
```
8.B) To view the directory structure please view https://github.com/Funlightingsystems/python-lights.
9. To connect it to the server running ola change the default IP address to connect to in the main.py script in the respective folders.
9.B) To edit files from the command line use the 'nano command'.
```
sudo nano main.py
```
10. Connect the lights to the Pi using the proper resistors and other electronic components as follows
| LED STRIP CONTACT PIN | RASPBERRY PI GPIO PIN |
|-----------------------|-----------------------|
| 5V                    | 17 (pwm)              |
| R,G,B                 | GND                   |
