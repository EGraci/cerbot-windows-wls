# Install Cerbot(WSL) on WLS Ubuntu in Windows

# windows system
1.   <img src="https://github.com/EGraci/cerbot-windows-wls/blob/main/developer-mode.PNG">
2.   <img src="https://github.com/EGraci/cerbot-windows-wls/blob/main/turn-windows-feature.PNG">
3.   <img src="https://github.com/EGraci/cerbot-windows-wls/blob/main/on-windows-features.PNG">
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
## configuration cerbot for apache or nginx
```
sudo apt install nginx
sudo apt install apache2
```
## genrate cerbot SSL
```
sudo certbot certonly --standalone -d [example.com] -d [www.example.com]
```
## Convert to .pfx or .cr
```
openssl pkcs12 -export -out cert.pfx -inkey privkey.pem -in fullchain.pem
```
