# Simple Notes App
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
apt-get update 
apt install nginx 
1. Clone the repository
```
git clone https://github.com/LondheShubham153/django-notes-app.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`


4. Copy the content in foler
   cd /django-notes-app/mynotes/build cp -r * /var/www/html (use sudo if you are not logged with the root user)
5. Use nginx proxy system
   cd /etc/nginx/sites-enabled/
   vi default and add proxy_pass http://127.0.0.1:8000; 
   just after the location
6. systemctl restart nginx
