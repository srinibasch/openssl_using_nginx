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

openssl: This is the basic command line tool for creating and managing OpenSSL certificates, keys, and other files.
req -x509: This specifies that we want to use X.509 certificate signing request (CSR) management. The “X.509” is a public key infrastructure standard that SSL and TLS adhere to for key and certificate management.

-nodes: This tells OpenSSL to skip the option to secure our certificate with a passphrase. We need Apache to be able to read the file, without user intervention, when the server starts up. A passphrase would prevent this from happening, since we would have to enter it after every restart.

-days 365: This option sets the length of time that the certificate will be considered valid. We set it for one year here.

-newkey rsa:2048: This specifies that we want to generate a new certificate and a new key at the same time. We did not create the key that is required to sign the certificate in a previous step, so we need to create it along with the certificate. The rsa:2048 portion tells it to make an RSA key that is 2048 bits long.

-keyout: This line tells OpenSSL where to place the generated private key file that we are creating.

-out: This tells OpenSSL where to place the certificate that we are creating.

<img src="https://raw.githubusercontent.com/srinibasch/openssl_using_nginx/main/1.jpg">

<img src="https://raw.githubusercontent.com/srinibasch/openssl_using_nginx/main/2.jpg">
6.open the nginx.conf


```
nano nginx.conf
```
7. edit the ssl part inside the nginx.conf

<img src="https://raw.githubusercontent.com/srinibasch/openssl_using_nginx/main/4.jpg">
8. restart nginx to load the changes


```
systemctl restart nginx
```
9.go to browser and load localhost(you should get https://localhost/ as your link)
<img src="https://raw.githubusercontent.com/srinibasch/openssl_using_nginx/main/5.jpg">
