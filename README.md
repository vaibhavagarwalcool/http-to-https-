# http-to-https-
http to https redirection for apache and nginx


http to https redirection for Apache
Open Apache configuration file
/etc/httpd/conf/httpd.conf
Add a rewrite rule to the VirtualHost section as below
<VirtualHost *:80>
RewriteEngine On
RewriteCond %{HTTP: X-Forwarded-Proto) =http
RewriteRule. https://%{HTTP: Host} & {REQUEST_URI} [L, R-permanent] </VirtualHost>
Save file and restart the service


Http to https redirection for Nginx
I
Open nginx configuration file: /etc/nginx/nginx.conf Add a below entry
server {
listen 80;
server_name _;
if ($http_x_forwarded_proto
'http'){
return 301 https://$host$request_uri;
}
}
Save file and restart the service
