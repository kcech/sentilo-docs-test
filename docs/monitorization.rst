Monitorization
==============

Background on Activity Monitor Agent
------------------------------------

Sentilo is a publication-subscription platform. The amount of data held
in the system is proportional to Redis deployment and directly depends
on the amount of physical memory available for the Redis server. In
another words, the data has to be probably deleted after a certain
amount of time to free the Redis memory. For example, in the Barcelona
deployment, the data is deleted after approximately one week.

Additionally to data expiration, Sentilo does not provide many
dashboards and those dashboards are not customizable.

In order to fill the gap of historization and dashboards, we use
`Elasticsearch <https://www.elastic.co/products/elasticsearch>`__ and
`Kibana <https://www.elastic.co/products/kibana>`__. Elasticsearch is a
powerful Java-based fulltext search database with REST API. It is
frequently used together with it’s modules, Kibana for dashboards and
Logstash for collecting of logs. The combination of Elasticsearch,
Logstash and Kibana is often called the ELK stack. ELK provides a
comfortable way to store and exploit historical information, and also a
near-realtime monitoring of the platform. Note that Elasticsearch
behaves excellently in cluster mode.

Sentilo events are uploaded to Elasticsearch through a Sentilo agent
called Activity Monitor Agent. The configuration of this agent is
described further in this chapter.

The following image illustrates a possible setup of Sentilo with ELK
stack. Logstash is optional and can be used e.g. for monitoring of
Sentilo logs (like login errors, invalid messages etc.), as well as
monitoring of system resources.

.. image:: _static/images/monitorization/sentilo_monitoring_deployment.png

The setup of the ELK stack is well documented and beyond the scope of
this page.

Configuration
-------------

Activity Monitor Agent is configured with a set of .properties files in
*sentilo/sentilo-agent-activity-monitor/src/main/resources/properties*.

**subsription.properties**

+-----------------------+-----------------------+-----------------------------------------+
| Property              | Description           | Comments                                |
+-----------------------+-----------------------+-----------------------------------------+
| topics-to-index       | Regexp pattern on     | Examples of configuration:              |
|                       | event name that       | ::                                      |
|                       | enables               |                                         |
|                       | including/excluding   |                                         |
|                       | events                |    /alarm/*,/data/*,/order/*            |
|                       |                       |                                         |
|                       |                       | Subscribes to all events                |
|                       |                       | ::                                      |
|                       |                       |                                         |
|                       |                       |    /data/PROVIDER1/*, /data/PROVIDER2/* |
|                       |                       |                                         |
|                       |                       |                                         |
|                       |                       | Subsribe only to data of 2 providers    |
|                       |                       |                                         |
+-----------------------+-----------------------+-----------------------------------------+ 

**monitor-config.properties**

+-----------------------+-----------------------+-----------------------+
| Property              | Description           | Comments              |
+-----------------------+-----------------------+-----------------------+
| elasticsearch.url     | URL of the ES         |                       |
|                       | instance              |                       |
+-----------------------+-----------------------+-----------------------+
| batch.size            | How many evens are    | Every HTTP request    |
|                       | sent to ES at once.   | consumes certain      |
|                       |                       | amount of resources,  |
|                       |                       | thus is convenient to |
|                       |                       | use a ES bulk API.    |
|                       |                       | The agent won't send  |
|                       |                       | events to ES until    |
|                       |                       | batch.size events     |
|                       |                       | occurred.             |
+-----------------------+-----------------------+-----------------------+
| batch.workers.size    | Number of threads the | Determines how many   |
|                       | agent                 | parallel threads      |
|                       |                       | communicate with ES.  |
+-----------------------+-----------------------+-----------------------+
| batch.max.retries     | Number of retries     | Number of intents for |
|                       | when ES is            | upload to ES          |
|                       | unavailable           | instance.             |
+-----------------------+-----------------------+-----------------------+


The agent will create index(es) called sentilo-YYYY-MM.

Configuration of Elasticsearch, Logstash and Kibana is beyond the scope
of this document and can be easily followed on their respective web
pages.

Compatible versions
-------------------

Sentilo has been successfully used in with these versions of ELK (which
does not mean other versions shouldn’t work as well):

-  Elasticsearch 2.3.1
-  Kibana 4.5.3
-  Logstash 2.3.2
