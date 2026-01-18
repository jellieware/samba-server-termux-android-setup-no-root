# samba-server-termux-android-setup-no-root
Samba server tutorial for Android
<br><br>
1] Install Samba Server on Termux:<br><br>

"pkg install samba"<br><br>

2] Add user with password<br><br>

a) Type "whoami"<br><br>

b) Copy username and replace it in the following line without asterixs:<br><br>

c) Type: "smbpasswd -L -c /data/data/com.termux/files/usr/etc/smb.conf -a *username*"<br><br>

d) Enter your password twice<br><br>

3] Edit smb.conf (I have uploaded a sample config you can look at, in the files section of this repo)<br><br>

a) The following lines have to be added to [globals]:<br><br>

   interfaces = 0.0.0.0/0<br>
# Allow connections from any IP address (less secure, use specific subnets for safety)<br>
   hosts allow = 0.0.0.0/0<br>
# Ensure Samba binds to the loopback for local access too<br>
   interfaces += 127.0.0.1/8<br><br>
   
   The port should be: 4445<br><br>
   
b) Make any other modifications you need then save the file!<br><br>

4] Start Samba Server:<br><br>

Type: smbd -D -s /data/data/com.termux/files/usr/etc/smb.conf<br><br>

5] Configure your samba client:<br><br>

The "share" name is important and needs to be included in the client config:<br><br>

<img width="1080" height="2400" alt="1000923963" src="https://github.com/user-attachments/assets/df722241-d4bd-498f-bafb-d27d922185be" />

<img width="1080" height="2400" alt="1000923964" src="https://github.com/user-attachments/assets/122649f4-6a34-4eee-ba8a-67f8db8cd081" />




