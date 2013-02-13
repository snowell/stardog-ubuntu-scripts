stardog-ubuntu-scripts
============

Licensed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)  
_Current Version **0.1**_ 

This is a library of scripts that allows for an easier time running the [Stardog RDF Database](http://stardog.com) on an Ubuntu server.

![Stardog](http://stardog.com/_/img/sdog.png)   

#Upstart#

The upstart folder contains a configuration script for a Stardog [Upstart](http://upstart.ubuntu.com/) job, allowing the Stardog server to run automatically at startup, shut down gracefully at system shutdown, and to be recovered automatically in case of system failure.  The folder also contains the sh scripts run by the job.

###Usage###

The scripts will expect that the following environment variables are set

* **$STARDOG_UID** - The uid of the user as which you wish to run the Stardog server
* **$STARDOG_GID** - The gid of the user as which you wish to run the Stardog server
* **$ROOTJAIL** - The location of the root jail in which you wish to run the Stardog server
* **$STARDOG_LOCATION** - The location of the Stardog installation, relative to $ROOTJAIL

Simply place stardog.conf into the /etc/init directory, and schild and sparent into $ROOTJAIL/$STARDOG_LOCATION.  As root, run "_start stardog_" to start the server