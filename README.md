# UCTRONICS Raspberry Pi Ultimate Rack | 0.91in OLED Display Code 
- Originally Titled: U6143_ssd1306
## Preparation | Raspberry PiOS
```bash
sudo raspi-config
```
Choose Interface Options 
Enable I2C
Exit Raspi Config, choosing "Yes" to reboot the system

## Install Dependencies
### For C
- build-essential
- wiringpi
```bash
sudo apt-get install build-essential -y && sudo apt-get install wiringpi -y
```
##  Clone U6143_ssd1306 library 
```bash
git clone https://github.com/ehbush/U6143_ssd1306.git
```
## Compile 
```bash
cd U6143_ssd1306/C
```
```bash
sudo make clean && sudo make 
```
## Run 
```
sudo ./display
```

## Automate Starting on Boot | Raspberry PiOS
- Open the rc.local file 
```bash
sudo nano /etc/rc.local
```
- Add command to the rc.local file
```bash
cd /home/pi/U6143_ssd1306/C
sudo make clean 
sudo make 
sudo ./display &
```
- Reboot the Pi
```bash
sudo reboot now
```

## For older 0.91 inch lcd without mcu 
- For the older version lcd without mcu controller, you can use python demo
- Install the dependent library files
```bash
sudo pip3 install adafruit-circuitpython-ssd1306
sudo apt-get install python3-pip
sudo apt-get install python3-pil
```
- Test demo 
```bash 
cd /home/pi/U6143_ssd1306/python 
sudo python3 ssd1306_stats.py
```










