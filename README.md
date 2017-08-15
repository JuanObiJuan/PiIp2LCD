# PiIp2LCD
This is a node app that shows your local ip (V4) to the grove LCD Backlight. You can later run the process after every boot.

# to run it:
git clone https://github.com/JuanObiJuan/PiIp2LCD
cd PiIp2LCD
node ip2lcd

# to run it on every boot in the raspberry pi
sudo vim /etc/rc.local

and leave it like

_IP=$(hostname -I) || true
if [ "$_IP" ]; then
  printf "My IP address is %s\n" "$_IP"
  node /home/pi/PiIp2LCD/ip2lcd.js
fi

exit 0                                                                                                                                    


