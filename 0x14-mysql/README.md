# MYSQL Intsall for version 5.7.
wget https://downloads.mysql.com/archives/get/p/23/file/mysql-5.7.38-linux-glibc2.12-x86_64.tar.gz
sudo tar -xzvf mysql-5.7.38-linux-glibc2.12-x86_64.tar.gz -C /usr/local/
sudo groupadd mysql
sudo useradd -r -g mysql -s /bin/false mysql
sudo cd /usr/local
sudo mv  mysql-5.7.38-linux-glibc2.12-x86_64 mysql
sudo cd mysql
sudo mkdir mysql-files
sudo chown mysql:mysql mysql-files
sudo chmod 750 mysql-files
sudo bin/mysqld --initialize --user=mysql
sudo bin/mysql_ssl_rsa_setup
sudo bin/mysqld_safe --user=mysql &
sudo  cp support-files/mysql.server /etc/init.d/mysql.server
sudo apt-get install libncurses5

export PATH=$PATH:/usr/local/mysql/bin
echo 'export PATH="$PATH:/usr/local/mysql/bin"' >> ~/.bashrc
