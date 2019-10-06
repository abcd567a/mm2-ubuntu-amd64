# mm2-ubuntu-amd64
### ModeSMixer2 installation script for Ubuntu 18.04 64bit Intel CPU
</br>

Copy-paste following command in SSH console and press Enter key. The script will install and configure modesmixer2. </br></br>
`sudo bash -c "$(wget -O - https://raw.githubusercontent.com/abcd567a/mm2-ubuntu-amd64/master/install-mm2.sh)" `</br></br>
After script finishes, it displays following message
```
=======================
INSTALLATION COMPLETED
=======================
PLEASE DO FOLLOWING:

(1) In your browser, go to web interface 
  From Computer on which you have installed modesmixer2:  
  http://localhost:8787 OR http://127.0.0.1:8787  
  From another computer on same local network:  
  http://ip-of-this-computer:8787  

(2) Open file mm2.sh for editing by following command:

sudo nano /usr/share/mm2/mm2.conf

Add following line: 

--location xx.xxxx:yy.yyyy 

(Replace xx.xxxx and yy.yyyy by your 
actual latitude and longitude) 
After entering location, Save (Ctrl+o) and Close (Ctrl+x) file md2.conf 
then restart mm2 by following command: 

sudo systemctl restart mm2



To see status sudo systemctl status mm2
To restart    sudo systemctl restart mm2
To stop       sudo systemctl stop mm2
```

### CONFIGURATION </br>
The configuration file can be edited by following command; </br>
`sudo nano /usr/share/mm2/mm2.conf ` </br></br>
**Default contents of config file**</br>
Default setting are for a decoder like dump1090-mutability or dump1090-fa running on the RPi. </br>
This can be changed by editing config file</br>
You can add extra arguments, one per line starting with `--` </br>
```
--inConnectId 127.0.0.1:30005:ADSB
--inConnectId 127.0.0.1:30105:MLAT
--web 8787

```
</br>

**To see all config parameters** </br>
```
cd /usr/share/mm2
./modesmixer2 --help
```

### UNINSTALL </br>
To completely remove configuration and all files, give following 4 commands:
```
sudo systemctl stop mm2 
sudo systemctl disable mm2 
sudo rm /lib/systemd/system/mm2.service 
sudo rm -rf /usr/share/mm2 
```
