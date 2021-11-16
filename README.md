# openssl_using_nginx
openssl_using_nginx
steps:-
1.login as root user                                              
```
sudo su
```
2.install nginx                                                   
```
yum install nginx
```
3.enable and start nginx                                          
```
systemctl enable nginx
```       
```

systemctl start nginx
```
4.go to etc and find nginx go inside nginx
```
cd /etc/nginx
```
5.inside /etc/nginx run the command to create ssl certificate (here i used msi as key name)
```
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout msi.key -out msi.crt
```
<img src="https://raw.githubusercontent.com/srinibasch/openssl_using_nginx/main/1.jpg">
<img src="https://raw.githubusercontent.com/srinibasch/openssl_using_nginx/main/2.jpg">
<img src="https://raw.githubusercontent.com/srinibasch/openssl_using_nginx/main/4.jpg">
<img src="https://raw.githubusercontent.com/srinibasch/openssl_using_nginx/main/5.jpg">
