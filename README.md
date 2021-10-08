# rproxy_shortcut
Nginx Reverse Proxy Shortcut Tool. This tool is to give you a simple UI in terminal to manage your nginx reverse proxy server. Like Adding subdomain in by just a second, whitelisting IP, blacklisting IP, Enabling/Disabling domains, Checking and applying configuration. 

==========Note from author===================

This is just a simple bash file to help you manage some of the nginx reverse proxy configuration and server setup.
I will make more updates for this since i have more ideas on what else is needed.
Like adding a function to add sub locations, multiple whitelisting for each domain and such.

So keep  looking for updates.

This is fully open source, feel free to explore/improve or let me know if you need any bug to fix or send your feedback,
or tell me what else did you upgrade this tool with.

email: 86kanth@gmail.com

Additional:

this tools will make changes in these directories:
1.) current directory .bashrc
2.) /bin
3.) /etc/nginx
4.) /etc/nginx/https
5.) /etc/nginx/https/domains
6.) content files stored at current directory /rproxy_files


===========After installation=========================


1.) EDIT THE NGINX DEFAULT FILE
    nano /etc/nginx/nginx.conf

2.) AND ADD THIS LINE inside http {} BEFORE THE CLOSING }
     include /etc/nginx/https/secured_sites.conf;

example:


http{
      log_format  main  '$remote_addr - $remote_user [$time_local] "$request" '
      '$status $body_bytes_sent "$http_referer" '
      '"$http_user_agent" "$http_x_forwarded_for"';
      include /etc/nginx/conf.d/*.conf;
  ......
  .....
  ....

  include /etc/nginx/https/secured_sites.conf;

}


 "===========SSL NOTE================="

 "Please place all your SSL certificates in these locations with the same name shown in below:"

 "SSL Certificate Location: /etc/pki/nginx/server.crt"
 "SSL Certificate Private-Key Location: /etc/pki/nginx/private/server.key"

 ----------------------------------
