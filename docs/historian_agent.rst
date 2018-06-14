Historian Agent
===============

Background on Historian Agent
-----------------------------

As you already might have learned, Sentilo does not persist data forever
because of limited system resources.

Commonly used setup of a Sentilo instance is to employ one of the agents
to copy the data into some external database or storage.

Since the data volumes can be fairly big and the data are mostly
structured (except when the observations are text), it is convenient to
use a scalable solution for time series such as
`OpenTSDB <http://opentsdb.net/>`__.

OpenTSDB installs of top of HBase and HDFS. Exposes a HTTP REST API and
can be used from `Grafana <http://grafana.org/>`__ as one of it’s
datasources.

Configuration
-------------

Historian Agent is configured with a set of .properties files in
sentilo/sentilo-agent-historian/src/main/resources/properties.

**subsription.properties**

+-----------------------+-----------------------+---------------------------------------+
| Property              | Description           | Comments                              |
+-----------------------+-----------------------+---------------------------------------+
| topics-to-index       | Regexp pattern on     | Examples of configuration             | 
|                       | event name that       | ::                                    |
|                       | enables               |                                       |
|                       | including/excluding   |    /alarm/*,/data/*,/order/*          |
|                       | events                |                                       |
|                       |                       |                                       |
|                       |                       | Subscribes to all events              |
|                       |                       | ::                                    |
|                       |                       |                                       |
|                       |                       | /data/PROVIDER1/*,/data/PROVIDER2/*   |
|                       |                       |                                       |
|                       |                       | Subsribes only to                     |
|                       |                       | data of 2 providers                   |
|                       |                       |                                       |
+-----------------------+-----------------------+---------------------------------------+  

**monitor-config.properties**

+-----------------------+-----------------------+-----------------------+
| Property              | Description           | Comments              |
+-----------------------+-----------------------+-----------------------+
| opentsdb.url          | URL of the OpenTSDB   |                       |
|                       | instance              |                       |
+-----------------------+-----------------------+-----------------------+
| batch.size            | How many evens are    | Every HTTP request    |
|                       | sent to OpenTSDB at   | consumes certain      |
|                       | once.                 | amount of resources,  |
|                       |                       | thus is convenient to |
|                       |                       | use a OpenTSDB bulk   |
|                       |                       | API. The agent won't  |
|                       |                       | send events to        |
|                       |                       | OpenTSDB until        |
|                       |                       | batch.size events     |
|                       |                       | occurred.             |
+-----------------------+-----------------------+-----------------------+
| batch.workers.size    | Number of threads the | Determines how many   |
|                       | agent                 | parallel threads      |
|                       |                       | communicate with      |
|                       |                       | OpenTSDB.             |
+-----------------------+-----------------------+-----------------------+
| batch.max.retries     | Number of retries     | Number of intents for |
|                       | when OpenTSDB is      | upload to OpenTSDB    |
|                       | unavailable           | instance.             |
+-----------------------+-----------------------+-----------------------+

Configuration of HDFS, HBase, OpenTSDB and is beyond the scope of this
document and can be easily followed on their respective web pages.

Compatible versions
-------------------

Sentilo has been successfully used in with these versions:

-  Hadoop 2.7.2
-  HBase 1.2.1
-  Opentsdb 2.2.0
-  Grafana 3.0.4
