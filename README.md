#ELK Server Configuration

#Install ElasticSearch from deb
```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-7.x.list
sudo apt-get update && sudo apt-get install elasticsearch
```

#Install kong
```
 sudo apt-get update
 sudo apt-get install -y apt-transport-https curl lsb-core
 echo "deb https://kong.bintray.com/kong-deb `lsb_release -sc` main" | sudo tee -a /etc/apt/sources.list
 curl -o bintray.key https://bintray.com/user/downloadSubjectPublicKey?username=bintray
 sudo apt-key add bintray.key
 sudo apt-get update
 sudo apt-get install -y kong
 ```

#Install Java Logstash
```
sudo apt install default-jdk

wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
sudo apt-get update && sudo apt-get install logstash
```

#Install Filebeat
```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
sudo apt-get update && sudo apt-get install filebeat
```

#Install Kibana
```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo apt-get install apt-transport-https
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
sudo apt-get update && sudo apt-get install kibana
```

#Configuration
Copy *.yml & *.conf to configuration folder on `/etc/<app>/filename`

#Running ELK
```
sudo service elasticsearch start
sudo service logstash start
sudo service filebeat start
sudo service kibana start
sudo kong start -c /path/to/kong.conf
```