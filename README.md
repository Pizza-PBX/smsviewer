INSIDE TERMINAL STEPS 

step 1) cd /var/www/html
step 2) make a directory named "sms" 
step 3) cd /var/www/html/sms 
step 4) then inside /var/www/html/sms you will create the 8 files same names same contents (there in the github the .php ones) the only 2 files you will need to nano and modify are config.php and login.php to add your credentials 
step 5) run these below 
chown -R asterisk:asterisk /var/www/html/sms
chmod -R 775 /var/www/html/sms

INSIDE BULKVS STEPS 
step 1) go to message webhooks and add a webhook with your pbx url followed by /sms/pizza.php (example http://123.456.789.0/sms/pizza.php)
step 2) if your pbx has a firewall unblock the bulkvs ips found in messaging instructions (there usually 52.206.134.245 or 192.9.236.42 though) 
step 3) go to DIDs - manage and select your DID that you purchased and click on view there 
- set messaging webhook to webhook name you just created 
- make sure to enable SMS 
- make sure you select your trunk group (this is created in interconnection though im assuming you already have it) 

* this will work with flowroute too just make sure to see there documentation of how to do it and what ips to unblock 
