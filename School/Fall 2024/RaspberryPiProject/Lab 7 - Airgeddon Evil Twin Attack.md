
Clone into the Airgeddon github repository
`sudo git clone https://github.com/v1s1t0r1sh3r3/airgeddon`
`cd airgeddon`

`sudo ./airgeddon.sh`
Once you run the command you will be prompted with a system check for dependencies. I had to manually install hostapd, isc-dhcp-server, lighttpd, xterm, and mdk4 to enable the options later. 
![[Pi5LAB07_Airgeddonlaunch.png]]

I Entered `3` into the terminal to choose the correct interface (needs to have monitor mode capabilities) 

![[Pi5LAB07_Airgeddoninterface.png]]

You will then be shown a menu with a variety of options. First I enabled monitor mode on the interface by entering `2` then `9` to select the correct Evil Twin AP attack (Captive portal)
![[Pi5LAB07_Airgeddoneviltwin.png]]
I entered `2` to choose the correct deauth attack
![[Pi5LAB07_Airgeddoneviltwindeauth.png]]
You will then be prompted to enable DoS pursuit mode which I was unable to do without a second interface. You can also spoof your MAC address which I did opt to do.
![[Pi5LAB07_Airgeddonaviltwincapture.png]]

![[Pi5LAB07_Airgeddoneviltwincaptiveportal.png]]


