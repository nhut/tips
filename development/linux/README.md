### Disable screen saver
$ sudo setterm -blank 0 -powersave off

### Check all files MD5 checksum in the folder where you are:
$ md5sum *

### Check specific files MD5 checksum (here for example file1.bin, file2.bin and file3.bin):
$ md5sum file1.bin file2.bin file3.bin

### Remove lines ends with png, jpg... from the file and remove line which contains "content to be removed"...:
$ egrep -iv "\.(png|jpg|jpeg|gif|pdf|svg|robot|mp3|py)$" input.txt > output.txt && egrep -v 'content to be removed\\subpath' output.txt > output2.txt && rm output.txt

### Mount CD/DVD-drive
$ sudo su #you don't need to run this if you are already in sudo mode
$ mkdir /media/dvd
$ mount /dev/cdrom /media/dvd

### VirtualBox install Virtual box guest additionals without UI
$ cd /media/dvd
$ ./VBoxLinuxAdditions.run --nox11 #--nox11 means there is no UI in this OS
$ cd
$ umount /media/dvd