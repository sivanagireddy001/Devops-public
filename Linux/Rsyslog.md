# Rsyslog
To set up `rsyslog` for log forwarding between two Ubuntu servers, you can follow the steps below:

# On the Source Server

1. Install rsyslog if it is not already installed
```
sudo apt-get update
```
```
sudo apt-get install rsyslog
```
Install the rsyslog into your server by default the configuration file path is `/etc/rsyslog.conf`.

2. Configure rsyslog to listen on the default port 514

```
sudo nano /etc/rsyslog.conf
```
Uncomment the following lines 

**For UDP** 
```
module(load="imudp")
input(type="imudp" port="514")
```
**For TCP**
```
module(load="imtcp")
input(type="imtcp" port="514")
```
Save and close the file.

3. Allow rsyslog through the firewall

**For UDP**
```
sudo ufw allow 514/udp
```
**For TCP**
```
sudo ufw allow 514/tcp
```
* Reload the firewall to apply the changes
```
sudo ufw reload
```
* To check the firewall status 
```
sudo ufw status
```
4. Restart the rsyslog service
```
sudo systemctl restart rsyslog
```
* To check the status of rsyslog service
```
sudo systemctl status rsyslog
```
* To enable the rsyslog service 
```
sudo systemctl enable rsyslog
```
<br></br>

# On the Target Server

1. Install rsyslog if it is not already installed
```
sudo apt-get update
sudo apt-get install rsyslog
```
Install the rsyslog into your server by default the configuration file path is `/etc/rsyslog.conf`.

2. Configure rsyslog to forward logs to the source server
```
sudo nano /etc/rsyslog.conf
```
Add the following line at the end of the file, replacing `source-server` with the `IP address` or `hostname` of the source server.

**For UDP**
```
*.* @source-server:514
```
**For TCP**
```
*.* @@source-server:514
```
Save and close the file.

3. Restart the rsyslog service
```
sudo systemctl restart rsyslog
```

<br></br>

**some useful rsyslog commands**
To check the rsyslog version type the below command
```
rsyslogd -v
```









