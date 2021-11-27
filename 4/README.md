### 4. install logstash in your system. download a sample nginx log from https://github.com/elastic/examples/blob/master/Common%20Data%20Formats/nginx_logs/nginx_logs , parse the logs using logstash. The parsed output must contain the geogriphical information like country, state etc. that the request is originating from. save the parsed output to a file in your system.
Steps:<br/>
Install logstash<br/>
Download and install the Public Signing Key:<br/>
```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
```
![wget](https://user-images.githubusercontent.com/53372486/143686272-d0e9ea4b-6e41-4cae-b246-4d81421ab606.png)<br/>

install the apt-transport-https package on Debian before proceeding<br/>
```
sudo apt-get install apt-transport-https
```
![tran](https://user-images.githubusercontent.com/53372486/143686278-5c59ff40-3d68-4100-b4ac-dac08d56625d.png)<br/>

add the Elastic source list to the sources.list.d directory, where APT will search for new sources<br/>
```
echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-7.x.list
```
![echo](https://user-images.githubusercontent.com/53372486/143686269-583398ba-c4b8-492f-a720-cbaaf5299e46.png)<br/>

Update APT and install logstash<br/>
```
sudo apt-get update && sudo apt-get install logstash
```
![install](https://user-images.githubusercontent.com/53372486/143686270-dc93619c-ad4d-42c0-848b-3a7c1b6a99ad.png)<br/>

Start logstash<br/>
```
sudo systemctl start logstash
```
Checking status<br/>
```
sudo systemctl status logstash
```
![status](https://user-images.githubusercontent.com/53372486/143686276-34bd585b-2191-4fa7-902b-dd0aad9a4f6c.png)<br/>



