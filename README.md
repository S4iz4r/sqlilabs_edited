
- sqli-labs is an extraordinary set of labs
specifically designed to exploit vulnerabilities based on sql injections,
that was originally created by Audi-1 "Dhakkan". Later it was modified by Rinkish to update it for php7.

- Rinkish left the work incomplete. More than a half of the laboratories, including some challenges,
were non-functional. I have taken the liberty of continuing with the work
and finishing modifying all the .php that did not work, thus leaving 100% of the labs functional.

¡¡¡¡¡¡ IMPORTANT NOTE !!!!!! 

# Do not expose these labs to the internet, that would lead to a severe security breach on your server.


########## Sqlilabs setup instructions ##########


Place sqlilabs folder into /var/www/html/

> apt install mariadb-server

> service mysql start
	  use mysql;
		  CREATE USER test IDENTIFIED BY 'test123'; or create the user you want, but remenber to modify the data in /sql-connections/db-creds.php
		  GRANT ALL PRIVILEGES ON *.* TO 'test'@'localhost' IDENTIFIED BY 'test123';
		  exit;
> service mysql restart

> apt install php-mysql

> phpenmod mysqli

> service apache2 start

Open the browser and go to http://localhost/sqlilabs

Click on "Setup/reset Database for labs" or go directly to http://localhost/sqlilabs/sql-connections/setup-db.php

If everything works fine, you should see a list of completed actions like this:

	SETTING UP THE DATABASE SCHEMA AND POPULATING DATA IN TABLES:

	[*]...................Old database 'SECURITY' purged if exists

	[*]...................Creating New database 'SECURITY' successfully

	[*]...................Creating New Table 'USERS' successfully

	[*]...................Creating New Table 'EMAILS' successfully

	[*]...................Creating New Table 'UAGENTS' successfully

	[*]....... and more...

	
If not, you should check that all the previous steps have been executed correctly.

There is the original sqli-labs repository created by Dhakkan: https://github.com/Audi-1/sqli-labs

If you want to see something different to "Dhakkan" in the welcome page, use this command:

	for i in $(find /var/www/html/sqlilabs -type f -name \*\.php); do sed -i 's/Dhakkan/<YourName>/g' $i; done

There is the repository of the modification that Rinkish made to update it to php7: https://github.com/Rinkish/Sqli_Edited_Version
 
Finally, I highly recommend viewing these videos from the original creator "Dhakkan": https://www.youtube.com/user/dhakkan3/videos

Useful MySQL SQL injection Cheat Sheet: http://pentestmonkey.net/cheat-sheet/sql-injection/mysql-sql-injection-cheat-sheet
