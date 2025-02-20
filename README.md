# ubuntu-conf
Configration files for Ubuntu server (currently 21.04)

sudo ufw allow 80/tcp<br>
sudo ufw allow 443/tcp<br>
sudo ufw allow 3306/tcp<br>
sudo ufw reload<br>
sudo ufw status<br>

sudo apt -y update && sudo apt -y upgrade<br>
sudo apt -y install apt-transport-https software-properties-common dirmngr gnupg2 unattended-upgrades cron-apt<br>

sudo wget https://raw.githubusercontent.com/Mintblok/ubuntu-conf/master/usr/bin/chweb -O /usr/bin/chweb && sudo chmod +x /usr/bin/chweb<br>
