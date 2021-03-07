## Improve Boot Time
Remove the default config `rm /etc/rc.conf` and edit by executing `nano /etc/rc.conf` and add the following:
```bash
# Global OpenRC configuration settings
rc_parallel="YES"
rc_interactive="NO"
rc_shell=/sbin/sulogin
rc_logger="NO"
rc_verbose="YES"
rc_nocolor=NO
unicode="YES"
SSD_NICELEVEL="-19"
rc_tty_number=12
rc_send_sighup="YES"
rc_timeout_stopsec="8"
rc_send_sigkill="YES"
```