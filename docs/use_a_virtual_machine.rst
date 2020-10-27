Use a Virtual Machine
=====================

A Sentilo sample instance is available for testing purposes distributed
as a Open Virtual Appliance file
(`OVA <https://en.wikipedia.org/wiki/Open_Virtualization_Format>`__).

The appliance is available for download
   `here <http://www.sentilo.io/wordpress/download/appliance/view(6).html>`__. It has been
   tested with **Virtual Box v5.0.40**.

The appliance contains the **1.9.0 Sentilo release** and runs Ubuntu Server 18.04.

Components installed:

-  Sentilo Catalog (web application)
-  Sentilo Platform Server (REST API)
-  Sentilo Relational Agent (saves the data to mySQL)
-  Sentilo Alert Agent
-  Sentilo Location Updater Agent

The virtual machine credentials are **sentilo/sentilo**.

All sentilo services are started automatically. The IP of the virtual machine is assigned
by the Virtualbox, to know which one is, enter the virtual machine and
execute the **“ifconfig”** command. You'l probably need'.

First steps:

-  Review the README file located in /home/sentilo.
-  The Catalog Console webapp will be ready to access in:
   http://your_ip:8080/sentilo-catalog-web/ with a access credentials:
   admin/1234
-  The API Rest endpoint will be listening for requests in:
   http://your_ip:8081
