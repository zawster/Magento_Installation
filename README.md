# Magento Installations Steps in Ubuntu
# Step 1: 
Install apache 2.4

sudo apt-get install apache2


# Step 2: 
Install the PHP extension

sudo apt-get install php7.0-fpm php7.0-mcrypt php7.0-curl php7.0-cli php7.0-mysql php7.0-gd php7.0-xsl php7.0-json php7.0-intl php-pear php7.0-dev php7.0-common php7.0-mbstring php7.0-zip php-soap libcurl3 curl -y
# If you still have problem in installation of php extentions, read my blog 
https://exxotics.wordpress.com/2018/09/14/how-to-solve-php-extension-bcmath-is-missing-when-installing-magento-in-ubuntu-16-04/#more-395
# Step 3: 
Install phpmyadmin

sudo apt install phpmyadmin

User: root

Pass: root

# Step 4: 
Download the sample data magento2

Permision html directory

sudo chmod -R 755 /var/www/html/magento/

Extract to / var / www / html / magento2 (your site's name)

# Step 5:
 Allow the directory
 
- Run the command on the root directory of magento:

sudo chown -R www-data: www-data /var/www/html/magento/

# Step 6:
 Install phpMyadmin (download zip file)
- https://www.phpmyadmin.net/

- Extract to / var / www / html / phpmyadmin

Yogurt:

Run: sudo apt install php libapache2-mod-php

- Create a database

# Step 7:
 Edit these files
 
    /etc/php/7.0/fpm/php.ini
    
    /etc/php/7.0/cli/php.ini
    
    /etc/php/7.0/apache2/php.ini

    max_execution_time = 1800
    
    max_input_time = 6000
    
    memory_limit = 1024M
    
    post_max_size = 128M
    
    upload_max_filesize = 32M

# Step 8:
 a2enmod rewrite apache
 
- run command:

        sudo a2enmod rewrite
        
- Insert into /etc/apache2/sites-available/000-default.conf:

    ＜Directory /var/www/html＞
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    ＜/ Directory＞


Restart apache2

# Step 9: Install magento2
# If you want to check the steps of Magento installation please read my blog
https://exxotics.wordpress.com/2018/09/29/install-and-configure-magento2-in-linux/#more-417
