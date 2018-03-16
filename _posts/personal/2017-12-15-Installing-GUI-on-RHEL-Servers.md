---
published: false
---
# Installing Gnome GUI on RHEL servers/local computers for desktop interfacing

**NOTE : ** This tutorial is only for RHEL servers, don't know how it will work with debian products

After searching a whole day, I get to know that this time only me can help myself.
So I went to Gnome IRC channel and asked for help but they given some reference on source code, not the whole script to do it.
this is what made my work worthy and finally, I was able to see the Gnome user interface through RDP
#### 1. Install Gnome GUI packages
##### for RHEL 
```
yum groupinstall "Server with GUI"
```
##### for CentOS 6/7
```
yum groupinstall "GNOME Desktop" "Graphical Administration Tools"
```

#### 2. Enable GUI on system startup. In CentOS 7 / RHEL 7,  systemd uses “targets” instead of runlevel. The /etc/inittab file is no more used to change run levels. So, issue the following command to enable the GUI on system start.

```
ln -sf /lib/systemd/system/runlevel5.target /etc/systemd/system/default.target
```

#### 3. Now what? just make a reboot
```
reboot
```

	