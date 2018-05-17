Create Alerts
=============

Description
-----------

This action allows to register one or more new alerts in the catalog.

::

   http://<your_api_server.com>/catalog/alert/<entity_id>

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Formats

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

POST

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

Writing

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Returns

.. raw:: html

   </th>

.. raw:: html

   <td>

No output data

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

The internal alerts should be defined through the catalog console or by
the API, but only using the catalog token.

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

alerts

.. raw:: html

   </td>

.. raw:: html

   <td>

Alerts list (alert) to register

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

Alert ID to register

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

Mandatory for internal, not applies for externals

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

Mandatory for internal, not applies for externals

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

ID of the component to which the sensor belongs

.. raw:: html

   </td>

.. raw:: html

   <td>

Mandatory for internal, not applies for externals

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

ID of the sensor to which the alert applies

.. raw:: html

   </td>

.. raw:: html

   <td>

Mandatory for internal, not applies for externals

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

Related entity identifier associated with the alert

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

-  The ID must identify an univocal alert, e.g., 2 alerts may not have
   the same ID.
-  The ID must have only alphanumeric (i.e. letters and numbers) and
   dashes characters, with no embedded spaces.
-  The list of trigger’s types and expressions are defined by the
   platform: `Trigger types <../alert/alert.html>`__.
-  The possible values ​​for the alert types are: INTERNAL or EXTERNAL.
-  Entity parameter is not mandatory, if empty the alert will be
   associated with the entity specified in the URL

Response data
-------------

This action doesn’t return additional data beyond the `HTTP status
code <../../general_model.html#reply>`__.

Examples
--------

Adding one external alert
~~~~~~~~~~~~~~~~~~~~~~~~~

If rec entity wants to register a new custom external alert with
REC_ALERT_001 identifier, to monitorize that maximum daily values for
sensor REC_001 ranged from 60 and 80, the request will be:

::

   http://<your_api_server.com>/catalog/alert/rec

and in the body message:

.. code:: json

   {"alerts":[
      {"id":"REC_ALERT_001",
       "name":"REC_ALERT_001",
       "description":"Custom alert to monitorize that maximum daily values for sensor REC_001 ranged from 60 and 80",
       "type":"EXTERNAL"
      }
   ]}

This request will register a new external alert with ID REC_ALERT_001
and associated to rec entity (i.e. rec entity is who will publish alarms
associated to this alert).

Remember, the external alerts are defined by third party
entities(providers or applications), which will be the responsibles of
calculating their logic and throw the related alarms when applies.

Adding one internal alert
~~~~~~~~~~~~~~~~~~~~~~~~~

If we want to register a new internal alert with ID REC_GT_45_ALERT_001,
to monitorize that values for sensor’s rec REC_001 are greater than 45,
the request to do is the following:

::

   http://<your_api_server.com>/catalog/alert/rec

and in the body message:

.. code:: json

   {"alerts":[
      {"id":"REC_GT_45_ALERT_001",
       "name":"REC_GT_45_ALERT_001",
       "description":"Internal alert to monitorize that values for sensor's rec REC_001 are greater than 45",
       "type":"INTERNAL",
       "trigger":"GT",
       "expression":"45",
       "component":"REC_COMP_001",
       "sensor":"REC_001"    
      }
   ]}

This request will register a new internal alert with REC_GT_45_ALERT_001
identifier and associated to REC_001 sensor which will publish an alarm
when sensor value will be greater than 45.

**This operation must be done using the catalog token.**
