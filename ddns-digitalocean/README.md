# ddns-digitalocean - Digital Ocean DNS updater script

This script update the given A record of your Domain hosted by Digital Ocean if the public IP was changed. 

Parameters:  
  - **subDomain:** The Name of A record in your DNS zone to update (must be already exist) 
  - **domainName:** The Domain Name hosted by Digital Ocean
  - **token:** Access Token for DigitalOcean API V2
  - **wanInterface:** The name of your interface with Public IP (pppoe, dhcp or static. Example: pppoe-wan)

*JParseFunctions script is used to parse JSON data, please get it from:*  
https://github.com/Winand/mikrotik-json-parser

Example scheduler (scheduled every 10 minutes):
```
/system scheduler
add interval=10m name=DO-DDNS on-event=ddns-digitalocean policy=ftp,reboot,read,write,policy,test,password,sniff,sensitive start-time=startup
```
