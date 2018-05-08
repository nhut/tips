### Hide apache warning for the text "Protocol not available: AH00076: Failed to enable APR_TCP_DEFER_ACCEPT"
mrx@ubuntu:~$ sudo /etc/init.d/apache2 start
[Tue May 08 13:09:23.487780 2018] [core:warn] [pid 491] (92)Protocol not available: AH00076: Failed to enable APR_TCP_DEFER_ACCEPT
To hide the warning:
$ sudo vim /etc/apache2/apache2.conf
Add following lines:
AcceptFilter https none
AcceptFilter http none