#Reverse-Proxy ShortCut-Installer Script By Kanthzone Networks
#Author Kanth Raj | 86kanth@gmail.com

me=1.0.2
env=readme

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
web: https://rproxy.kanthzone.com
blog: https://writings.kanthzone.com

Additional:

this tools will make changes on these directories:<br>
1.) current directory .bashrc<br>
2.) /bin<br>
3.) /etc/nginx<br>
4.) /etc/nginx/https<br>
5.) /etc/nginx/https/domains<br>
6.) content files stored at current directory /rproxy_files<br>

===========INSTALLATION=========================<br>

1.) wget https://github.com/C0D3RLK/rproxy_shortcut/archive/refs/heads/main.zip<br>
OR<br>
you may clone the git file <br>
git clone https://github.com/C0D3RLK/rproxy_shortcut.git<br>


2.) If you downloaded the ZIP file <br>
*make sure you have installed the unzip tool<br>

<b>unzip main.zip<br>

cd rproxy_shortcut-main/<br>

this will startup the instllation:<br>
. get_rproxy_shortcut<br>

</b>

do the same with the downloaded git file find the "get_rproxy_shortcut" run it with bash.
<br>



===========After installation=========================


1.) EDIT THE NGINX DEFAULT FILE
    nano /etc/nginx/nginx.conf

2.) AND ADD THIS LINE inside http {} and BEFORE THE CLOSING }<br>
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

 "Please place all your SSL certificates in these locations with the same name shown in below:"<br>

 "SSL Certificate Location: /etc/pki/nginx/server.crt"<br>
 "SSL Certificate Private-Key Location: /etc/pki/nginx/private/server.key"

 ----------------------------------



===========TEMPLATE =========================


This package comes with preset nginx server config template.
 You may change the template to suite your setup at:


THE HEADER TEMPLATE - contains all the server & ssl related  setup
 /<your root directory>/rproxy_files/top.config


THE FOOTER TEMPLATE - Contain Error File directories
/<your root directory>/rproxy_files/bottom.config



===========UPDATING =========================

Just type UPDATE and enter, the script will look for our versioning file and will let you know on the changes.
::you can always choose not to use this feature.

#>: UPDATE



===========DELETING / REMOVING =========================

Just type DEL and enter, the tool will remove it self and restore your previous environment.

#>: DEL


===========OTHER NOTE =========================

Do not remove these files and directories, it will break the script functionality.
<br>
##FILES<br>
/<your user/root directory>/bashrc.bak<br>
/etc/nginx/conf.d/whitelist.conf<br>
/bin/rproxy<br>
<br>

##DIRECTORIES<br>
/<your user/root directory>/rproxy_files<br>
/etc/nginx/<br>
/etc/nginx/https/<br>
/etc/nginx/https/domains<br>
