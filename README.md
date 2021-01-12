# nginx-macos-catalina10.15.7

### Installations
`brew install nginx`

### Test localhost
`browser http://localhost:8080`

### Check nginx configuration
`vi /usr/local/etc/nginx/nginx.conf`

### Change server default to listen 8080

`
server {
        listen       8080;
        server_name  localhost;
`
- **change listen: 8080 later, if test is successful**

### Go to servers dir
`vi /usr/local/etc/nginx/servers/nginx.conf`

### Copy paste below: **Change <USERS> to your folder
    server {
      listen 8080;
      server_name dev.nginx;


      location / {
        root /Users/<USERS>/Projects/G_github;
        index index.html index.htm;
      }
    }


### Create Directory
`
mkdir -p /Users/<USERS>/Projects/G_github
`

### Create index.html
`cd /Users/<USERS>/Projects/G_github`
`echo "HELLO WORLD!!" >> index.html`

### add hostname "dev.nginx" to /etc/hosts
`vi /etc/hosts`

### input below to /etc/hosts
`127.0.0.1 dev.nginx`

### restart nginx
`brew services restart nginx`
