## MATERI DEPLOYMENT

### TUTORIAL SETUP NEXTJS

1. git clone https://github.com/repository-yang-mau-kalian-deploy
2. cd repository-yang-mau-kalian-deploy
3. npm install
4. npm run build
5. npm run start

### TUTORIAL NGINX

1. apt update
2. apt install -y nginx
3. cd /etc/nginx
4. cd sites-available
5. vi web

```
server {
  listen 80;

  server_name _;

  location / {
    proxy_pass http://localhost:3000;
  }
}
```

6. sudo unlink /etc/nginx/sites-enabled/default
7. sudo ln -s /etc/nginx/sites-available/web /etc/nginx/sites-enabled/web
8. sudo nginx -s reload
