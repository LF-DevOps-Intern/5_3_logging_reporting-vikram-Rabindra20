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

Download nginx log<br/>
```
wget https://raw.githubusercontent.com/elastic/examples/master/Common%20Data%20Formats/nginx_logs/nginx_logs
```
![wgetlog](https://user-images.githubusercontent.com/53372486/143729344-96fe6faa-9489-4e62-95ba-2ca10ee63865.png)<br/>

Change Dir<br/>
```
cd /etc/logstash
```
Add path in logstash.yml <br/>
```
path.config: /etc/logstash/conf.d
```
Change Dir<br/>
```
cd /etc/logstash/conf.d
```
Add below code inside logstach.conf<br/>
```
input {
  file {
    type => "nginx-log"
    path => "/home/rabindra/nginx_log/nginx_logs.log"
    sincedb_path => "/dev/null"
   start_position => "beginning"}
}
filter {
grok{
match=>{
"message"=>"%{IP:clientip} \- \- \["
}
}
geoip {
source => "clientip"
}
}
output {
  file {
   path => "/var/log/logstash/geonginx.log"    }
}
```
![conf](https://user-images.githubusercontent.com/53372486/143729282-602a6d14-1d1d-4b72-ac7f-86b9e04579d9.png)<br/>

Change Dir<br/>
```
cd /usr/share/logstash/
```
Run logstash<br/>
```
sudo bin/logstash --path.settings /etc/logstash --path.data sensor39 -f /home/rabindra/etc logstash/conf.d
```
![run](https://user-images.githubusercontent.com/53372486/143729285-08f7e75d-a1f2-41a5-a0d3-e1624bfb9c97.png)<br/>

Change Dir<br/>
```
cd /var/log/logstash
```
![ls](https://user-images.githubusercontent.com/53372486/143729283-d5509abb-008a-440b-b3ce-e2a6fac1c1c9.png)<br/>

Check file<br/>
```
cat geonginx.log 
```
![output](https://user-images.githubusercontent.com/53372486/143729287-3b0435a9-1fbb-436d-8ab3-a1b4c1454db6.png)



