# XAMMP_VIRTUALHOST_SETUP in UBUNTU

# 1)
    lammp/etc/httpd.conf
    unable "Include etc/extra/httpd-vhosts.conf" by removing # 

# 2)
Than change/add below code in "lammp/etc/extra/httpd.vhost.conf"
    <VirtualHost 127.0.0.2:80>
        ServerAdmin localhost.myweb.com
        DocumentRoot "/opt/lampp/htdocs/thaiquiz"
        ErrorLog "logs/dummy-host2.example.com-error_log"
        CustomLog "logs/dummy-host2.example.com-access_log" common
    </VirtualHost>
    <VirtualHost *:80>
      DocumentRoot "/opt/lampp/htdocs/"
      <Directory "/opt/lampp/htdocs/">
        Options All
        AllowOverride All
        Require all granted
      </Directory>
    </VirtualHost>
 
# 3)Than add below line in "etc/hosts"
    127.0.0.2	localhost.myweb.com
