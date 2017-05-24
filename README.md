#Udacity Linux Server Configuration Project

##IP Address and SSH Port for reviewer access of server
13.58.123.129 port 2200
See notes to reviewer for private SSH key for grader user to sign in. (I'm using uda_grader in ~/.ssh dir)

##Complete URL to hosted web application

##Summary of Software Installed
    * Software Updated via `apt-get upgrade` resulting in 155 package updates 71 of which were security updates.
    *

##Summary of configuration changes made
    * add grader user with sudo privileges
    * sshd_config modified to only allow ssh connections on port 2200, also
    * deny all incoming ports via ufw except 2200 for ssh, 80 for http, 123 for ntp. Allow all outgoing
    

##List of third-party resources used to complete Project
