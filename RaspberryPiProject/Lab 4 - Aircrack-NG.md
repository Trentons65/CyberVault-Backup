![[Pi5LAB04_AirmonWifi.png]]1. Once you are connected to the WiFi network, ensure that your Raspberry Pi is updated using the following command: `sudo apt update && sudo apt full-upgrade -y`.
2. We need to ensure that all of the Kali Linux Wireless tools are installed: `sudo apt install kali-tools-wireless`
3. Setup Raspberry Pi in monitor mode. This is a multi-step process and we will be taking advantage of the aircrack-ng suite ([www.aircrack-ng.orgLinks to an external site.](http://www.aircrack-ng.org/)). This tool is actually installable in other Linux distributions.  
Step 1: Check WiFi related processes and kill them: `sudo airmon-ng check`There are processes that will interfere with monitor mode and should be disabled with the command: `sudo airmon-ng check kill`  
Step 2: Set in-built wireless adapter (or external adapter) for monitor mode: If you are using an external wireless adapter, it might be wlan1 instead of wlan0, depending on your configuration.  
    sudo airmon-ng start wlan0
4. Test the monitor mode by issuing the following command: `sudo airodump-ng wlan0mon`
5. Proceed with the following commands only if you own the network or you have explicit and written permissions to test the wireless network.  
    Perform an injection test by issuing the following command:  
    Another Important point, if you are in the classroom performing the text, you are only allowed to test against the provided network.  
    `sudo aireplay-ng --test wlan0mon -b «bssid of access point»`
6. Now that you have tested the WiFi sniffing and was able to gather experience using this powerful tool, we need to reset the WiFi adapter to normal operation. You will execute the following commands: `sudo airmon-ng stop wlan0mon`
7. Restart Network Manager using the command: `sudo systemctl start NetworkManager`