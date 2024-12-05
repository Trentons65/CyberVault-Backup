`adb install apkfilename.apk`
[Configure the Burp Proxy listener](https://support.portswigger.net/customer/portal/articles/1841101-configuring-an-android-device-to-work-with-burp)

Installing trusted CA at the Android OS level (Root device/Emulator) for Android N+ as the following:

  

`openssl x509 -inform PEM -subject_hash -in BurpCA.pem | head -1`

`cat BurpCA.pem > 9a5ba580.0`

`openssl x509 -inform PEM -text -in BurpCA.pem -out /dev/null >> 9a5ba580.0`

`adb root`

`abd remount`

`adb push 9a5ba580.0 /system/etc/security/cacerts/`

`adb shell "chmod 644 /system/etc/security/cacerts/9a5ba580.0"`

`adb shell "reboot"`

`adb shell`

**[Inspect SQLite db via a GUI tool](https://sqlitebrowser.org/dl/)**

Pull the file from device first, then use a GUI software to look the schema and content. I use SQLite browser which allows you to see the database schema, table content, as well as executing some simple SQL scripts.

`adb pull /data/data/package-name/databases/sqlitedatabse`

**Inspect SQLite db via sqlite3 command line tool**

For me the easier option is to use sqlite3 command line tool to inspect the database from adb shell.

`cd data/data/package-name/databases/`

`sqlite3 db-name`

`.tables`

`.schema table-name`


