### 3. Create a file in your system. Whenever a someone performs some action(read, write, execute) on that file, the event should be logged somewhere. 
Steps:<br/>
Install auditd<br/>
```
sudo apt install auditd
```
![auditd](https://user-images.githubusercontent.com/53372486/143687847-e3e74368-e7cb-4859-8e52-1af7353607fa.png)<br/>

Start Service<br/>
```
sudo service auditd start
```
![start](https://user-images.githubusercontent.com/53372486/143687844-775845b2-a734-4a52-bbca-a73d50e880b8.png)<br/>

Enable auditd<br/>
```
sudo systemctl enable auditd
```
Checking status<br/>
```
systemctl status auditd
```
![status](https://user-images.githubusercontent.com/53372486/143687846-63d172a2-a294-4baf-9304-ed3b5b7c9cb2.png)<br/>

Make dir and files
```
mkdir file 
mkdir log 
```
![dir](https://user-images.githubusercontent.com/53372486/143687839-4535d15e-4983-4bab-a401-0b2fe3ba9483.png)<br/>

Add rule for File<br/>
```
sudo auditctl -w /home/rabindra/file/file.txt -p rwa -k /home/rabindra/log/log.log
```
![auditctlhome](https://user-images.githubusercontent.com/53372486/143687845-4d77605e-73b3-412a-ba92-40044b1be276.png)<br/>

Current status of the audit system can be view<br/>
```
sudo auditctl -s
```
![-s](https://user-images.githubusercontent.com/53372486/143687843-2816ffc1-9bc5-4ca9-a033-d8663849ae76.png)<br/>

View the rule set<br/>
```
sudo auditctl -l
```
![-l](https://user-images.githubusercontent.com/53372486/143687842-65488575-856c-4042-af3e-33a57fd44034.png)<br/>

Show log<br/>
```
sudo ausearch -k /home/rabindra/log/log.log
```
![ausearch](https://user-images.githubusercontent.com/53372486/143687849-180a215d-cd1c-4372-8d43-42007e041ee4.png)<br/>



