1. Update apt:
```
sudo apt update
```
2. Install git:
```
sudo apt install git
```
3. Install node:
```
curl -sL https://deb.nodesource.com/setup_20.x | sudo bash - 
sudo apt install -y nodejs
```
4. Install npm
```
sudo apt install npm
```
5. Install pm2:
```
sudo npm install pm2@latest -g
```
7. Install Nginx:
```
sudo apt install nginx
```
8. Clone the repo: (replace with your repo)
```
git clone https://github.com/evel2903/BotAdapter
```
9. Install dependencies: (Replace with your folder)
```
cd BotAdapter
npm install
```
10. Run the server using pm2
```
pm2 start npm --name "trading-server" -- start
```
11. Update nginx file:
```
cd /etc/nginx/sites-available

sudo nano default
```

Update with this content
```
server {
    listen 80 default_server;
    listen [::]:80 default_server;

    location / {
        proxy_pass http://localhost:3000;
    }
}
```
To exit and save:
```
Ctrl + X --> Y
```

Test to make sure there is no error:

```
sudo nginx -t
```

Restart Nginx:

```
```
