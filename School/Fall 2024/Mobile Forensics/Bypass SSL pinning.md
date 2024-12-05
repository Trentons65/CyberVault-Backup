## Frida

`pip install frida-tools`  - Install 

`frida --version` - Check version

`adb push /path/serverfrida /data/local/tmp` - Unzip file and push

`adb shell chmod 777 /data/local/tmp/frida-server`  - Permissions

### Launch server

`adb shell /data/local/tmp/frida-servername&`
`frida-ps -U`