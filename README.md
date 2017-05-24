#Udacity Linux Server Configuration Project

##IP Address and SSH Port for reviewer access of server
13.58.123.129 port 2200
See notes to reviewer for private SSH key for grader user to sign in. (I'm using uda_grader in ~/.ssh dir)

##Complete URL to hosted web application
http://ec2-13-58-123-129.us-east-2.compute.amazonaws.com/

##Summary of Software Installed
    * Software Updated via `apt-get upgrade` resulting in 155 package updates 71 of which were security updates.
    * Installed Apache HTTP Server (apache2)
    * Installed mod_wsgi (libapache2-mod-wsgi) and python-dev
    * Installed git (git-all)
    * Installed postgresql
    * Installed python-pip and subsequtently pip install'ed virtualenv
    * inside of the virtualenv(catalog) I pip installed required dependencies for the application
        - Flask, sqlalchemy, httplib2, requests, psycopg2, oauth2client

##Summary of configuration changes made
    * add grader user with sudo privileges
    * sshd_config modified to only allow ssh connections on port 2200, also
    * deny all incoming ports via ufw except 2200 for ssh, 80 for http, 123 for ntp. Allow all outgoing
    * apache config file modified to respond to requests with wsgi, enabled with sudo a2enmod wsgi
    * created environment variable user for postgres (-u postgres createuser -s $USER)
    * Modified /etc/apache2/sites-enabled/000-default.conf to send all requests to flaskapp.wsgi which points to the item catalog.


##List of third-party resources used to complete Project
    * https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
    * http://newcoder.io/scrape/part-0/
    * https://discussions.udacity.com/t/how-to-move-a-flask-app-from-using-a-sqlite3-db-to-postgresql/7004/4
    * http://killtheyak.com/use-postgresql-with-django-flask/
    * http://flask.pocoo.org/docs/0.10/deploying/mod_wsgi/
