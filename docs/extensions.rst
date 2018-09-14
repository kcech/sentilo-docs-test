Extensions
==========

Agents
------

Agents are internal modules oriented to expand its functionality without
having to alter its core. The installation is based on the principle of
Plug & Play: they are recognized by the system and started automatically
to be up and running.

Every agent is a process that acts as a subscriber for the
publish/subcribe platform. These processes will subscribe directly to
Redis as a independent clients. This subscription will provide the input
data to do the underlying business logic (store in a relational
database, process alarms, generate statistics, …)

The following diagram shows the design that every agent should follow:

.. image:: _static/images/extensions/arch6.jpg

1. When agent is started, it subscribes as client to Redis for the event
   that wants to receive notifications.
2. When Redis receives a publication of any of these data, the agent is
   automatically notified with a new message.
3. The message is processed and transferred to the corresponding agent’s
   service responsible to carry out the underlying business logic.

As mentioned above, Sentilo currently provides two agents:

Relational database agent
~~~~~~~~~~~~~~~~~~~~~~~~~

This agent stores all information received from PubSub platform into a
set of relational databases (the number of relational databases is fully
configurable). It could be configured to filter the data to store
according to a business rules through a configuration file.

To do this, when the agent is started it makes a subscription to the
desired information in Redis (observations, orders and/or alarms), that
has previously been defined in a properties file:

::

   //In this example we indicate to persist any data using a DataSource with srDs identifier, 
   //and also to store any data from provider with PARKING identifier, 
   //on a different DataSource whose identifier is parkingDs.

   //Finally, we can indicate more than one DataSource destination to persist the same data.

   data\:PARKING*=parkingDs
   data\:*=srDs
   order\:*=srDs
   alarm\:*=srDs,parkingDs

It is imperative that the DataSources are defined in the context of the
agent with the same identifier:

.. code:: xml

   <bean id="srDs" class="org.apache.commons.dbcp.BasicDataSource" 
      destroy-method="close"> 
      ...
   </bean> 

   <bean id="parkingDs" class="org.apache.commons.dbcp.BasicDataSource" 
      destroy-method="close"> 
    ...
   </bean>

This context is defined in the file:

::

   sentilo-agent-relational/src/main/resources/spring/relational-persistence-context.xml

Alarm agent
~~~~~~~~~~~

This agent processes each internal alert defined in the catalog and
publish a notification (a.k.a. *alarm*) when any of the configured
integrity rules are not met.

Due to the type of available rules, this validation process integrity is
divided into two threads:

-  An internal process that runs every minute, evaluates the status of
   each sensor that have associated (*frozen* type) alerts.
-  Additionally, each time a Redis notification is received, alerts
   associated with the data received are evaluated.

Finally, an internal process regularly synchronize the alert list, to
synchronize the information stored in memory with the catalog
repository.

Activity Monitor agent
~~~~~~~~~~~~~~~~~~~~~~

This agent subscribes itself to the list of events and uploads them to
an ElasticSearch database. More on its configuration and an overview of
Sentilo monitoring is on this `dedicated
page <./monitorization.html>`__.

Historian agent
~~~~~~~~~~~~~~~

Likewise the Activity Monitor Agent, this module also subscribes itself
to the list of events and uploads them to an OpenTSDB database. More on
its configuration is on this `dedicated page <historian_agent.html>`__.

Node-red
--------

`Node-RED <https://nodered.org>`__ offers a fast integration and
prototyping ecosystem for Sentilo. There’s a Sentilo ad-hoc node in
/sentilo-node-red. In order to activate it to your local Node-RED
installaction procede with two simple steps:

1. From the directory /sentilo-node-red, type:

::

   npm link

This command registers the package node-red-contrib-sentilo to the
NodeJS node_modules.

2. In order to add the module to your NOdeRED installation, type:

::

   cd ~/.node-red
   npm link node-red-contrib-sentilo

Then, following nodes should appear in the nodes palette:

.. image:: _static/images/extensions/sentilo-nodered.png

Now, you should be able to use Sentilo from Node-RED:

.. image:: _static/images/extensions/sentilo-nodered2.png
