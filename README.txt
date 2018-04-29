
README FILE 

PROJECT LINK AND IP ADDRESS :
----------------------------
Check out the project by clicking the following link!

http://ec2-18-130-36-145.eu-west-2.compute.amazonaws.com/ 
ip address: 18.130.36.145 port:2200
--------------------------------------------------------------------------------------------------------------------

PROJECT DESCRIPTION :
---------------------
* THE PROJECT WILL REFLECT THE THEME OF RESTAURANTS AND MENUITEMS
* USERS COULD LOG IN AND LOG OUT OF THE WEB APP 
* USERS ARE ALLOWED TO LOGIN IN THROUGH A GOOGLE PLUS ACCOUNT 
* A lOGGED IN USER COULD EDIT , DELETE AND ADD A NEW RESTAURENT  

 
WHAT IS INCLUDED :
--------------------
__init__.py >> The main python file that contains the code for the web application.
Static folder >> contains the style for the webpage and two images which are used in the web application.
Templates folder >> contains the HTML pages used by the web application, each web page has its own HTML Page.
database_setup.py >> to create a database on SQLALCHEMY using restaurant, User and Menu tables specified with their columns.
lotsofmenus.py >> this folder contains data that should be populated in the database. 
clients_secrets.json >> this file contains the info for the google client that is associated for that project.


CONFIGURATIONS AND SOFTWARE INSTALLATIONS:
------------------------------------------
*Installed PYTHON, APACHE2, MOD-WSGI, FLASK, POSTGRESQL
*Configured flask.config to have the following info 
<VirtualHost *:80>
        ServerName http://ec2-18-130-36-145.eu-west-2.compute.amazonaws.com
        ServerAdmin heba.mahmoud1994.hm@gmail.com
        WSGIScriptAlias / /var/www/FlaskApp/flaskapp.wsgi
        <Directory /var/www/FlaskApp/ItemCatalogProject/>
                Order allow,deny
                Allow from all
        </Directory>
        Alias /static /var/www/FlaskApp/ItemCatalogProject/static
        <Directory /var/www/FlaskApp/ItemCatalogProject/static/>
                Order allow,deny
                Allow from all
        </Directory>
        Alias /static /var/www/FlaskApp/ItemCatalogProject/templates
        <Directory /var/www/FlaskApp/ItemCatalogProject/templates/>
                Order allow,deny
                Allow from all
        </Directory>
        ErrorLog ${APACHE_LOG_DIR}/error.log
        LogLevel warn
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
*configured flaskapp.wsgi to have the following info 
#!/usr/bin/python
import sys
import logging
logging.basicConfig(stream=sys.stderr)
sys.path.insert(0,"/var/www/FlaskApp/ItemCatalogProject")

from __init__ import app as application
application.secret_key = 'grader'

* SHH KEY LOCATION FOR GRADER: .ssh/authorized_keys
