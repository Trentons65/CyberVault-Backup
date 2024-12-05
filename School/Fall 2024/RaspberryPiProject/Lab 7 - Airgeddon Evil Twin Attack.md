
Clone into the Airgeddon github repository
`sudo git clone https://github.com/v1s1t0r1sh3r3/airgeddon`
`cd airgeddon`

`sudo ./airgeddon.sh`
Once you run the command you will be prompted with a system check for dependencies. I had to manually install hostapd, isc-dhcp-server, lighttpd, xterm, and mdk4 to enable the options later. 

![Pi5LAB07_Airgeddonlaunch](https://github.com/user-attachments/assets/a48054f6-2d7c-42da-95a4-849e159dd4c3)


I Entered `3` into the terminal to choose the correct interface (needs to have monitor mode capabilities) 

![Pi5LAB07_Airgeddoninterface](https://github.com/user-attachments/assets/dc0eb2a1-1988-441a-87df-e35f0b6c8061)

You will then be shown a menu with a variety of options. First I enabled monitor mode on the interface by entering `2` then `9` to select the correct Evil Twin AP attack (Captive portal)
![Pi5LAB07_Airgeddoneviltwin](https://github.com/user-attachments/assets/fc2f47a1-1e58-4fd7-8aaa-73a9713b3097)

I entered `2` to choose the correct deauth attack
![Pi5LAB07_Airgeddoneviltwindeauth](https://github.com/user-attachments/assets/02cb0b9f-4a67-4e7f-930e-d78065f5d665)

You will then be prompted to enable DoS pursuit mode which I was unable to do without a second interface. You can also spoof your MAC address which I did opt to do.
![Pi5LAB07_Airgeddonaviltwincapture](https://github.com/user-attachments/assets/ba8801ca-525b-4392-9d5f-aeee50b30b7c)

You will need a host connected to the AP in order to capture a handshake

![Pi5LAB07_Airgeddoneviltwincaptiveportal](https://github.com/user-attachments/assets/6987fa9a-a506-4023-8bde-8eef51294eef)




