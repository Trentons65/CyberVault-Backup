#### Connected pi5 to my windows pc through ethernet and assigned an ip to pi5
![[Pi5LAB03_PcEthConnection.png]]
![[Pi5LAB03_PiEthConnection.png]]
## Windows
On the computer that you are connecting to the Raspberry Pi, use the following command to generate a ssh key pair:

`ssh-keygen`

Follow the prompts and configure the key. You can optionally include a passphrase for the key using the ssh-keygen process.

![[Pi5LAB03_SSH.png]]
#### Used “type .ssh\id_rsa.pub | ssh kali@(ipaddress) “mkdir -p ~/.ssh/authorized_keys” to ssh the keys to the pi5

Copy your public key (id_rsa.pub) to your Raspberry Pi using the command:

`ssh-copy-id pi@«Raspberry Pi IP address| Raspberry Pi name»`.

You will need to provide the password to your Raspberry PI in order to connect and install the key. This only works on a UNIX or UNIX-like system as the command is missing from a Windows system. In order to Copy ssh keys from Windows machine, use the following command:

`type .ssh\id_rsa.pub | ssh USER@HOST "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"`

![[Pi5LAB03_sshdpubkey.png]]
#### (Further connection tests used key as shown by ssh daemon)
## Mac / Linux

If you are using a Macintosh or a Linux-based machine, you may use the following command to add your key to the keychain (on Macintosh) or OpenSSH authentication agent (on Linux) and thus never have to enter the passphrase:

`ssh-add -K ~/.ssh/id_rsa`