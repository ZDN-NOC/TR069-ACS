**INSTALL GENIEACS**
```
apt update
apt upgrade
apt install curl
wget https://raw.githubusercontent.com/ZDN-NOC/TR069-ACS/main/genie.sh
chmod +x genie.sh
./genie.sh
```

Selanjutnya silahkan buka URL genie acs IP:3000.
Lanjutkan dengan update Config, Provisioning dan Virtual Parameter

```
mkdir /root/db
cd /root/db
wget https://raw.githubusercontent.com/ZDN-NOC/TR069-ACS/main/config.bson
wget https://raw.githubusercontent.com/ZDN-NOC/TR069-ACS/main/config.metadata.json
wget https://raw.githubusercontent.com/ZDN-NOC/TR069-ACS/main/presets.bson
wget https://raw.githubusercontent.com/ZDN-NOC/TR069-ACS/main/presets.metadata.json
wget https://raw.githubusercontent.com/ZDN-NOC/TR069-ACS/main/provisions.bson
wget https://raw.githubusercontent.com/ZDN-NOC/TR069-ACS/main/provisions.metadata.json
wget https://raw.githubusercontent.com/ZDN-NOC/TR069-ACS/main/virtualParameters.bson
wget https://raw.githubusercontent.com/ZDN-NOC/TR069-ACS/main/virtualParameters.metadata.json
mongorestore --db genieacs --drop /root/db
systemctl start genieacs-{cwmp,ui,nbi}
```
