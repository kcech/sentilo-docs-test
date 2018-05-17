Retrieve Authorized Alerts
==========================

Description
-----------

This action returns the list of alerts for which the entity_id could do
a subscription, i.e., alerts that belongs to entity_id or alerts for
which entity_id has read permission over its owner. In addition, the
service also allows you to specify search criteria to filter alerts to
be retrieved: filter by alert type and / or filter by trigger type.

::

    http://<your_api_server.com>/catalog/alert/<entity_id>?<parameter>=<value>

The entity_id is optional and can be an Application or a Provider.

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Format

.. raw:: html

   </th>

.. raw:: html

   <td>

json

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Method

.. raw:: html

   </th>

.. raw:: html

   <td>

GET

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Permission

.. raw:: html

   </th>

.. raw:: html

   <td>

Reading

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Return

.. raw:: html

   </th>

.. raw:: html

   <td>

List of authorized alerts

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Parameters
----------

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Key

.. raw:: html

   </th>

.. raw:: html

   <th>

Description

.. raw:: html

   </th>

.. raw:: html

   <th>

Optional

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

type

.. raw:: html

   </td>

.. raw:: html

   <td>

Alert’s type filter

.. raw:: html

   </td>

.. raw:: html

   <td>

Yes

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

trigger

.. raw:: html

   </td>

.. raw:: html

   <td>

Trigger’s type filter

.. raw:: html

   </td>

.. raw:: html

   <td>

Yes

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Please, note the following observations:

-  The list of trigger’s types available are defined by the platform:
   `Trigger types <../alert/alert#InternalTriggerTypes>`__.
-  The possible values ​​for the alert type is also defined by the
   platform and are: INTERNAL, EXTERNAL.

Response data
-------------

As commented before, this action, in addition to the `HTTP status
code <../../general_model#reply>`__, returns the list of alerts for
which entity_id has at least read permission.

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Key

.. raw:: html

   </th>

.. raw:: html

   <th>

Description

.. raw:: html

   </th>

.. raw:: html

   <th>

Optional

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

alerts

.. raw:: html

   </td>

.. raw:: html

   <td>

Alerts list (alert)

.. raw:: html

   </td>

.. raw:: html

   <td>

Not

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Every alert element has the following structure:

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Key

.. raw:: html

   </th>

.. raw:: html

   <th>

Description

.. raw:: html

   </th>

.. raw:: html

   <th>

Optional

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

id

.. raw:: html

   </td>

.. raw:: html

   <td>

Alert ID

.. raw:: html

   </td>

.. raw:: html

   <td>

No

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

name

.. raw:: html

   </td>

.. raw:: html

   <td>

Alert name

.. raw:: html

   </td>

.. raw:: html

   <td>

Yes

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

description

.. raw:: html

   </td>

.. raw:: html

   <td>

Alert description

.. raw:: html

   </td>

.. raw:: html

   <td>

Yes

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

entity

.. raw:: html

   </td>

.. raw:: html

   <td>

Related entity

.. raw:: html

   </td>

.. raw:: html

   <td>

No

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

type

.. raw:: html

   </td>

.. raw:: html

   <td>

Alert type

.. raw:: html

   </td>

.. raw:: html

   <td>

No

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

trigger

.. raw:: html

   </td>

.. raw:: html

   <td>

Trigger type

.. raw:: html

   </td>

.. raw:: html

   <td>

No, but only returned for internal alerts

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

expression

.. raw:: html

   </td>

.. raw:: html

   <td>

Expression to evaluate with the trigger

.. raw:: html

   </td>

.. raw:: html

   <td>

No, but only returned for internal alerts

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

component

.. raw:: html

   </td>

.. raw:: html

   <td>

Component identifier to which the sensor belongs

.. raw:: html

   </td>

.. raw:: html

   <td>

No, but only returned for internal alerts

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

sensor

.. raw:: html

   </td>

.. raw:: html

   <td>

Sensor identifier to which the alert applies

.. raw:: html

   </td>

.. raw:: html

   <td>

No, but only returned for internal alerts

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Examples
--------

Request to retrieve all the authorized alerts
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following request shows an example to retrieve all the authorized
alerts for rec entity:

::

    http://<your_api_server.com>/catalog/alert/rec

and the response will be:

.. code:: json

   {
     "alerts" : [
       {
         "id" : "REC_ALERT_001",
         "name" : "REC_ALERT_001",
         "description" : "Custom alert to monitorize that maximum daily values for sensor REC_001 ranged from 60 and 80",
         "entity" : "SAMCLA",
         "type" : "EXTERNAL"
       },
       {
         "id" : "REC_ALERT_002",
         "name" : "REC_ALERT_002",
         "description" : "Internal alert to check if S00020114-0 value is greater than 45",
         "entity" : "SAMCLA",
         "type" : "INTERNAL",
         "trigger" : "GT",
         "expression" : "45",
         "component" : "S00020114",
         "sensor" : "S00020114-0"
       }
     ]
   }

Request to retrieve all the authorized alerts filtered by type and trigger
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following request shows an example to retrieve all internal alerts
for rec entity with trigger type equal to GT.

::

    http://<your_api_server.com>/catalog/alert/rec?type=INTERNAL&trigger=GT

and the response will be:

::

   {"alerts":[
      {
         "id" : "REC_ALERT_002",
         "name" : "REC_ALERT_002",
         "description" : "Internal alert to check if S00020114-0 value is greater than 45",
         "entity" : "SAMCLA",
         "type" : "INTERNAL",
         "trigger" : "GT",
         "expression" : "45",
         "component" : "S00020114",
         "sensor" : "S00020114-0"
       } 
   ]}
