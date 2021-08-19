# ubuntu-conf
Configration files for Ubuntu server (currently 21.04)

ufw allow 80/tcp<br>
ufw allow 443/tcp<br>
ufw allow 3306/tcp<br>
ufw disable && ufw --force enable<br>
ufw status<br>

apt -y update && apt -y upgrade 
apt -y install apt-transport-https software-properties-common dirmngr gnupg2 ufw unattended-upgrades cron-apt 

wget https://raw.githubusercontent.com/iboosting/ubuntu-conf/master/usr/bin/chweb -O /usr/bin/chweb && chmod +x /usr/bin/chweb 
rm /etc/apt/sources.list && rm /etc/apt/sources.list~ 
wget https://raw.githubusercontent.com/iboosting/ubuntu-conf/master/etc/apt/sources-us.list -O /etc/apt/sources.list 
wget https://raw.githubusercontent.com/iboosting/ubuntu-conf/master/etc/apt/sources.list.d/ondrej.list -O /etc/apt/sources.list.d/ondrej.list 
wget https://raw.githubusercontent.com/iboosting/ubuntu-conf/master/etc/apt/sources.list.d/mariadb.us.list -O /etc/apt/sources.list.d/mariadb.list 

apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8 
apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0x4F4EA0AAE5267A6C 

LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php 

echo "deb [arch=amd64] http://nginx.org/packages/ubuntu `lsb_release -cs` nginx" \ 
    | sudo tee /etc/apt/sources.list.d/nginx.list 
curl -fsSL https://nginx.org/keys/nginx_signing.key | sudo apt-key add - 

apt-key adv --recv-keys --keyserver hkp://keyserver.ubuntu.com:80 0xF1656F24C74CD1D8 
add-apt-repository 'deb [arch=amd64] http://mirror.rackspace.com/mariadb/repo/10.6/ubuntu hirsute main' 
