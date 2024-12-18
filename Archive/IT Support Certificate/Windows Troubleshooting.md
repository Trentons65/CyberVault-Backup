**Accessing logs** - eventvwr.msc

Utilize custom filters to search for relevant logs

Event levels: Critical, error, warning, verbose and information

Sort by log/ source

Always document conclusions

**TOOLS**

- **Windows Update:** One of the most important repair tools for Windows problems. Widespread and known Windows problems will often have a software resolution provided by Microsoft or Original Equipment Manufacturers (OEMs). Windows Update will find, download, and install the required and/or recommended software resolutions, which include operating system patches and updates, security updates and fixes, .NET framework updates, driver and firmware updates, etc. 

- **Updates from the hardware manufacturer(s)**: Some OEM updates are not accessible through Windows Update. For these items, it is necessary to go to the OEM’s website for updates, patches, drivers, and firmware for components such as computer hardware, peripherals, and third-party applications.  
   
- **Optimize Drives with Disk Defragmenter:** When files on a hard drive are saved, deleted, or altered, fragmentation across storage blocks can occur. A file may become spread across the drive in non-contiguous storage blocks. This issue results in performance problems within the system as the hard drive spends additional seek time finding the scattered file fragments and piecing them back together. The Windows Disk Defragmenter can automatically relocate file fragments onto a continuous series of storage blocks in order to remedy these seek time delays. 

- **Disk Cleanup:** Windows utility that simplifies removing temporary files including downloaded program files, thumbnail files, system files, and temporary internet files. Disk Cleanup also offers an option to compress the primary hard drive where the Windows OS resides. 

- **CHKDSK command:** A command-line utility for Windows that scans hard drives to find and flag bad sectors. Flagged bad sectors will be removed from use and no data will be stored on them. The tool will attempt to recover any data found on the bad sector.  
   
- **Disk Management tool:** A Windows system utility for performing advanced storage management tasks, including initializing a new drive, extending or shrinking a volume, and changing a drive letter.

- **Registry Editor (regedit):** The Registry Editor should only be used by advanced system administrators. It is possible to cause serious system and software problems if the wrong edits are made to the Registry. 

- **System Configuration tool (msconfig):** Software tool for changing system settings, including the services and applications that can load on system startup.  
   
- **Safe Mode (Windows 10 and 11):** There are multiple options for booting into safe mode. A couple of these options include:

    - **System Configuration tool** - Can be used to configure a clean boot in Safe Mode to help isolate the source of a system problem.
    
    - **Startup Settings** - Can be accessed through **System > Recovery** or through the sign-in screen.

- **System Troubleshoot tool (Windows 11):** The Windows Troubleshoot menu can be accessed from **Start > Settings > System > Troubleshoot**. The following options are available on the Troubleshoot menu:
    
    - **Recommended troubleshooter preferences** - Set preferences for Microsoft’s recommendations for troubleshooting tools.
        
    - **Recommended troubleshooter history** - Easy access to troubleshooting tools used previously.
        
    - **Other troubleshooters** - This menu includes tools for troubleshooting internet connections, audio, printers, Windows Update, Bluetooth, camera, incoming connections, keyboard, network adapter, power, program compatibility, search & indexing, shared folders, video, Windows Store apps, privacy, and misc help. 
        

## Common problems in Windows

The following is a list of common problems encountered in Windows, along with common troubleshooting first steps:  

- **Computer is running slowly:** There are many issues that could make a computer run slowly. Troubleshooting can involve multiple steps, many of which should be performed on a regular schedule to proactively prevent problems from happening. The first step should almost always be to reboot the computer. This step can fix a large percentage of problems reported by end users. If rebooting does not resolve the problem, check that there is sufficient processing power, disk space, and RAM to support the OS, hardware, software, and intended use of the computer. For example, video editing may require a relatively more powerful computer, a large amount of free hard drive space, and lots of RAM. Check system event logs for errors. Research any error codes found using the Microsoft knowledge base or an internet search to see if there is a known solution to the problem. Run an antivirus and anti-malware scan. Use Windows Update and OEM updates to ensure the system is up to date. Remove temporary and unneeded files and software. Check the software and services that load at startup for potential problem sources. Reboot the computer into Safe Mode to see if the computer performance improves. Unplug peripherals and turn off network connections to eliminate these as sources of the slow down. If the OS is Windows 11, use the System Troubleshoot tools found at **Start > Settings > System > Troubleshoot.**
    
- **Computer is frozen:** Power off the computer. Wait 30 seconds to drain residual power and clear any potentially corrupted data held by RAM. Boot up the computer again and check system event logs. If the system does not boot, go to the BIOS settings and boot into Safe Mode to gain access to the event logs. Research any error codes found. If the root cause cannot be determined, run the same checks as listed above for “Computer is running slowly”.
    
- **Blue screen errors:** If the blue screen provides an error code or QR code, record this information in order to research the root cause of the issue and possible solutions. Power off the computer, wait 30 seconds, then boot the computer again. If the system does not boot, go into the BIOS settings to boot into Safe Mode. Obtain system event logs in the Windows Event Viewer and research any error codes found there. If the root cause cannot be determined through event codes within the logs, then run the same checks as listed above for “Computer is running slowly”.  
    
- **Hardware problems:** Check the hardware OEM’s website for updates to drivers, firmware, and software management consoles. If this does not resolve the problem, check the system Device Manager to see if the device has been disabled or is not recognized. Additionally, check system event logs and research any error codes found. If the root cause cannot be determined, then run the same checks as listed above for “Computer is running slowly”.  
    
- **Software problems:** Go to the software manufacturer’s website to check for software patches or updates. If the problem continues after updating the software, check the application event logs and research any error codes found. If the root cause cannot be determined, then run the same checks as listed above for “Computer is running slowly”.  
    
- **Application is frozen:** End application processes in Task Manager. Restart application. If the problem persists, reboot the computer and try to run the application again. If the issue is still not resolved, then follow the instructions listed above for software problems.
    
- **A peripheral is not working:** Check to ensure the peripheral is on and is receiving sufficient power, especially if the item is battery powered. Check cables to ensure they are attached securely. If the item is connected through USB, try a different USB port. If the device connects through Bluetooth, check to ensure that Bluetooth is active on both the computer and the peripheral. Reboot the computer to see if the system can reconnect to the device. Inexpensive, high-use peripheral devices experience high failure rates, especially keyboards and mice. Swap the peripheral for a working replacement to see if the problem was the peripheral itself, or perhaps an error in how the computer is detecting the peripheral. If the problem persists with the replacement peripheral, check the system Device Manager to see if the device has been disabled or is not recognized. Check the event logs for any errors. Visit the OEM’s website to look for updates to drivers, firmware, and/or software management consoles, if available. Run a Windows Update as well. 
    
- **Audio problems:** Check audio volume. Run the Windows audio troubleshooter. Check speaker cables, plugs, jacks, and/or headphones. Check sound settings. Update or repair audio drivers and sound card firmware. Check to ensure the active and default audio devices are the desired audio devices. Turn off audio enhancements. Stop and restart audio services in Task Manager. Restart the computer. Research if specific audio CODECs are needed for audio media. If audio is not working in a browser, ensure the browser has permission to use the system audio and/or microphone.