# Install Cerbot(WSL) on WLS Ubuntu in Windows

# windows system
1.
<img src="https://github.com/EGraci/cerbot-windows-wls/blob/main/developer-mode.PNG">
2.
<img src="https://github.com/EGraci/cerbot-windows-wls/blob/main/turn-windows-feature.PNG">
3.
<img src="https://github.com/EGraci/cerbot-windows-wls/blob/main/on-windows-features.PNG">
## configurate WSL on windows

## install WLS on Windows
```
wsl --install
```
after finish restart the windows and setting new username and password

## path WLS Ubuntu certificates
```
\\wsl$\Ubuntu\etc\letsencrypt\live\
```
# ubuntu system

## install cerbot on WLS Ubuntu
```
sudo apt install certbot python3-certbot-nginx
```
## genrate cerbot SSL
```
sudo certbot certonly --manual --preferred-challenges=http -d [example.com]
```
## make folder web sever Nginx or Apache
```
[path-webserver]/.well-known/acme-challenge
```
## and make file with name the intruction certbot like this
```
...
http://example.com/.well-known/acme-challenge/[this the name]
```
## fill the file name with the data on the intruction certbot like this
```
Create a file containing just this data:

[this value]
...
```
## Convert to .pfx or .cr
```
openssl pkcs12 -export -out cert.pfx -inkey privkey.pem -in fullchain.pem
```
## convert to apache xampp windows
```
sudo cp /etc/letsencrypt/live/[yourdomain.com]/fullchain.pem move to  --> /xampp/apache/conf/ssl.crt/server.crt
sudo cp /etc/letsencrypt/live/[yourdomain.com]/privkey.pemm ove to  --> /xampp/apache/conf/ssl.key/server.key
```
