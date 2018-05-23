Catalog
=======

.. toctree::
   :hidden:
   :titlesonly:
   :maxdepth: 1
   
   create_sensors
   update_sensors
   retrieve_authorized_entities
   delete_component_or_sensor



Description
-----------

The catalog service allows to register or modify your own
sensors/components or query the characteristics of a sensor or provider.

All requests for this service will have the following format:

::

    http://<your_api_server.com>/catalog/<provider_id>

where provider_id is optional and should be included depending on the
operation.

Actions
-------

The available actions for this service are:

-  `Adding components / sensors <./create_sensors.html>`__
-  `Update data components / sensors <./update_sensors.html>`__
-  `Retrieve list of providers /
   sensors <./retrieve_authorized_entities.html>`__
-  `Remove components / sensors <./delete_component_or_sensor.html>`__

Component types
---------------

The list of component types should be configured for each Sentilo
instance, the following list could be used as a reference for any city:

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Id

.. raw:: html

   </th>

.. raw:: html

   <th>

Name

.. raw:: html

   </th>

.. raw:: html

   <th>

Description

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

temperature

.. raw:: html

   </th>

.. raw:: html

   <td>

Temperature

.. raw:: html

   </td>

.. raw:: html

   <td>

Temperature measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

noise

.. raw:: html

   </th>

.. raw:: html

   <td>

Soundmeter

.. raw:: html

   </td>

.. raw:: html

   <td>

Sound measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

wind

.. raw:: html

   </th>

.. raw:: html

   <td>

Anemometer

.. raw:: html

   </td>

.. raw:: html

   <td>

Wind speed

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

humidity

.. raw:: html

   </th>

.. raw:: html

   <td>

Humidity

.. raw:: html

   </td>

.. raw:: html

   <td>

Humidity measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

air_quality

.. raw:: html

   </th>

.. raw:: html

   <td>

Air Quality

.. raw:: html

   </td>

.. raw:: html

   <td>

Air Quality control

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

water_quality

.. raw:: html

   </th>

.. raw:: html

   <td>

Water Quality

.. raw:: html

   </td>

.. raw:: html

   <td>

Water Quality control

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

meteo

.. raw:: html

   </th>

.. raw:: html

   <td>

Meteorology

.. raw:: html

   </td>

.. raw:: html

   <td>

Weather Station

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

parking

.. raw:: html

   </th>

.. raw:: html

   <td>

Occupation parking

.. raw:: html

   </td>

.. raw:: html

   <td>

Parking control

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

luminosity

.. raw:: html

   </th>

.. raw:: html

   <td>

Luminosity

.. raw:: html

   </td>

.. raw:: html

   <td>

Luminosity measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

glass_container

.. raw:: html

   </th>

.. raw:: html

   <td>

Occupancy container level

.. raw:: html

   </td>

.. raw:: html

   <td>

Glass occupancy container measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

paper_container

.. raw:: html

   </th>

.. raw:: html

   <td>

Occupancy container level

.. raw:: html

   </td>

.. raw:: html

   <td>

Paper occupancy container measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

plastic_container

.. raw:: html

   </th>

.. raw:: html

   <td>

Occupancy container level

.. raw:: html

   </td>

.. raw:: html

   <td>

Plastic occupancy container measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

organic_container

.. raw:: html

   </th>

.. raw:: html

   <td>

Occupancy container level

.. raw:: html

   </td>

.. raw:: html

   <td>

Organic occupancy container measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

refuse_container

.. raw:: html

   </th>

.. raw:: html

   <td>

Occupancy container level

.. raw:: html

   </td>

.. raw:: html

   <td>

Refuse occupancy container measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

container_volum

.. raw:: html

   </th>

.. raw:: html

   <td>

Occupancy container level

.. raw:: html

   </td>

.. raw:: html

   <td>

Generic occupancy container measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

soil_moisture

.. raw:: html

   </th>

.. raw:: html

   <td>

Soil moisture

.. raw:: html

   </td>

.. raw:: html

   <td>

Soil moisture measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

park_meter

.. raw:: html

   </th>

.. raw:: html

   <td>

Parking meter

.. raw:: html

   </td>

.. raw:: html

   <td>

Parking meter control

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

traffic

.. raw:: html

   </th>

.. raw:: html

   <td>

Traffic

.. raw:: html

   </td>

.. raw:: html

   <td>

Traffic measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

people_flow

.. raw:: html

   </th>

.. raw:: html

   <td>

People flow

.. raw:: html

   </td>

.. raw:: html

   <td>

Pedestrian flow measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

flowmeter

.. raw:: html

   </th>

.. raw:: html

   <td>

Water flow

.. raw:: html

   </td>

.. raw:: html

   <td>

Water flow measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

solenoid_valve

.. raw:: html

   </th>

.. raw:: html

   <td>

Electrovalve

.. raw:: html

   </td>

.. raw:: html

   <td>

Solenoid control

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

salinity

.. raw:: html

   </th>

.. raw:: html

   <td>

Salinity

.. raw:: html

   </td>

.. raw:: html

   <td>

Soil salinity measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

internal_ambient_conditions

.. raw:: html

   </th>

.. raw:: html

   <td>

Internal Environmental Conditions

.. raw:: html

   </td>

.. raw:: html

   <td>

Temperature, humidity and luminosity measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

external_ambient_conditions

.. raw:: html

   </th>

.. raw:: html

   <td>

External environmental conditions

.. raw:: html

   </td>

.. raw:: html

   <td>

Temperature, humidity and luminosity measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

network_analyzer

.. raw:: html

   </th>

.. raw:: html

   <td>

Network analyzer

.. raw:: html

   </td>

.. raw:: html

   <td>

Electric network analyzer

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

gas_meter

.. raw:: html

   </th>

.. raw:: html

   <td>

Gas meter

.. raw:: html

   </td>

.. raw:: html

   <td>

Gas consumption meter

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

electricity_meter

.. raw:: html

   </th>

.. raw:: html

   <td>

Electricity meter

.. raw:: html

   </td>

.. raw:: html

   <td>

Electricity consumption meter

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

water_meter

.. raw:: html

   </th>

.. raw:: html

   <td>

Water meter

.. raw:: html

   </td>

.. raw:: html

   <td>

Water consumption meter

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

soil_sensor

.. raw:: html

   </th>

.. raw:: html

   <td>

Soil sensor

.. raw:: html

   </td>

.. raw:: html

   <td>

Soil mesurement of salinity, mosture, etc

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

generic

.. raw:: html

   </th>

.. raw:: html

   <td>

Generic component type

.. raw:: html

   </td>

.. raw:: html

   <td>

Default component type if not specified

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

plugsense

.. raw:: html

   </th>

.. raw:: html

   <td>

Plug & Sense

.. raw:: html

   </td>

.. raw:: html

   <td>

Plug & Sense Libelium component

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Sensor types
------------

The list of sensor types should be configured for each Sentilo instance,
the following list could be used as a reference for any city:

.. raw:: html

   <table>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Id

.. raw:: html

   </th>

.. raw:: html

   <th>

Name

.. raw:: html

   </th>

.. raw:: html

   <th>

Description

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

temperature

.. raw:: html

   </th>

.. raw:: html

   <td>

Temperature

.. raw:: html

   </td>

.. raw:: html

   <td>

Temperature measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

noise

.. raw:: html

   </th>

.. raw:: html

   <td>

Soundmeter Class II

.. raw:: html

   </td>

.. raw:: html

   <td>

Sound level measuring class II.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

noise_class_i

.. raw:: html

   </th>

.. raw:: html

   <td>

Soundmeter Class I

.. raw:: html

   </td>

.. raw:: html

   <td>

Sound level measuring class I

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

anemometer

.. raw:: html

   </th>

.. raw:: html

   <td>

Anemometer

.. raw:: html

   </td>

.. raw:: html

   <td>

Wind Speed ​measuring

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

humidity

.. raw:: html

   </th>

.. raw:: html

   <td>

Humidity

.. raw:: html

   </td>

.. raw:: html

   <td>

Humidity measuring

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

parking

.. raw:: html

   </th>

.. raw:: html

   <td>

Occupation parking

.. raw:: html

   </td>

.. raw:: html

   <td>

Occupation parking control

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

luminosity

.. raw:: html

   </th>

.. raw:: html

   <td>

Luminosity

.. raw:: html

   </td>

.. raw:: html

   <td>

Luminosity measuring

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

container_volum

.. raw:: html

   </th>

.. raw:: html

   <td>

Occupancy container level

.. raw:: html

   </td>

.. raw:: html

   <td>

Occupancy container measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

container_overturn

.. raw:: html

   </th>

.. raw:: html

   <td>

Container overturned

.. raw:: html

   </td>

.. raw:: html

   <td>

Container overturned indicator

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

container_open

.. raw:: html

   </th>

.. raw:: html

   <td>

Container open

.. raw:: html

   </td>

.. raw:: html

   <td>

Container opening indicator

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

status

.. raw:: html

   </th>

.. raw:: html

   <td>

Sensor status

.. raw:: html

   </td>

.. raw:: html

   <td>

Status control

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

battery

.. raw:: html

   </th>

.. raw:: html

   <td>

Battery level

.. raw:: html

   </td>

.. raw:: html

   <td>

Battery level measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

soil_moisture_15

.. raw:: html

   </th>

.. raw:: html

   <td>

Soil moisture 15 cm.

.. raw:: html

   </td>

.. raw:: html

   <td>

Soil moisture measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

soil_moisture_35

.. raw:: html

   </th>

.. raw:: html

   <td>

Soil moisture 35 cm.

.. raw:: html

   </td>

.. raw:: html

   <td>

Soil moisture measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

park_meter

.. raw:: html

   </th>

.. raw:: html

   <td>

Parking meter

.. raw:: html

   </td>

.. raw:: html

   <td>

Parking meter control

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

vehicle_volume

.. raw:: html

   </th>

.. raw:: html

   <td>

Number of vehicles

.. raw:: html

   </td>

.. raw:: html

   <td>

Measurement of number of vehicles

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

vehicle_occupation_average

.. raw:: html

   </th>

.. raw:: html

   <td>

Average occupancy

.. raw:: html

   </td>

.. raw:: html

   <td>

Measurement of average occupancy in vehicles

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

vehicle_speed

.. raw:: html

   </th>

.. raw:: html

   <td>

Speed ​​Vehicle

.. raw:: html

   </td>

.. raw:: html

   <td>

Vehicle speed ​​measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

air_quality_no2

.. raw:: html

   </th>

.. raw:: html

   <td>

NO2

.. raw:: html

   </td>

.. raw:: html

   <td>

Nitrogen dioxide measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

air_quality_pm10

.. raw:: html

   </th>

.. raw:: html

   <td>

PM10

.. raw:: html

   </td>

.. raw:: html

   <td>

Measurement of suspension particles PM10

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

air_quality_pm25

.. raw:: html

   </th>

.. raw:: html

   <td>

PM25

.. raw:: html

   </td>

.. raw:: html

   <td>

Measurement of supsension particles PM25

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

air_quality_o3

.. raw:: html

   </th>

.. raw:: html

   <td>

O3

.. raw:: html

   </td>

.. raw:: html

   <td>

Ozone measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

air_quality_so2

.. raw:: html

   </th>

.. raw:: html

   <td>

SO2

.. raw:: html

   </td>

.. raw:: html

   <td>

Sulfur dioxide measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

air_quality_co

.. raw:: html

   </th>

.. raw:: html

   <td>

CO

.. raw:: html

   </td>

.. raw:: html

   <td>

Carbon Monoxide measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

air_quality_co2

.. raw:: html

   </th>

.. raw:: html

   <td>

CO2

.. raw:: html

   </td>

.. raw:: html

   <td>

Carbon dioxide measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

people_flow

.. raw:: html

   </th>

.. raw:: html

   <td>

People flow

.. raw:: html

   </td>

.. raw:: html

   <td>

Measurement of pedestrian flow

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

flowmeter

.. raw:: html

   </th>

.. raw:: html

   <td>

Water flow

.. raw:: html

   </td>

.. raw:: html

   <td>

Water flow measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

solenoid_valve

.. raw:: html

   </th>

.. raw:: html

   <td>

Electrovalve

.. raw:: html

   </td>

.. raw:: html

   <td>

Solenoid actuator

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

eto

.. raw:: html

   </th>

.. raw:: html

   <td>

Evotranspiration

.. raw:: html

   </td>

.. raw:: html

   <td>

Evotranspiration measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

salinity

.. raw:: html

   </th>

.. raw:: html

   <td>

Salinity

.. raw:: html

   </td>

.. raw:: html

   <td>

Soil salinity measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

pluviometer

.. raw:: html

   </th>

.. raw:: html

   <td>

Pluviometer

.. raw:: html

   </td>

.. raw:: html

   <td>

Rain measurement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

rain

.. raw:: html

   </th>

.. raw:: html

   <td>

Rain gauge

.. raw:: html

   </td>

.. raw:: html

   <td>

Rain indicator (it’s raining/it’s not raining)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

wind

.. raw:: html

   </th>

.. raw:: html

   <td>

Wind gauge

.. raw:: html

   </td>

.. raw:: html

   <td>

Wind indicator (>X m/s)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

wind_direction_6_m

.. raw:: html

   </th>

.. raw:: html

   <td>

Wind direction

.. raw:: html

   </td>

.. raw:: html

   <td>

Wind direction at 6 meters

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

wind_direction_10_m

.. raw:: html

   </th>

.. raw:: html

   <td>

Wind direction

.. raw:: html

   </td>

.. raw:: html

   <td>

Wind direction at 10 meters

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

voltage

.. raw:: html

   </th>

.. raw:: html

   <td>

Voltmetre

.. raw:: html

   </td>

.. raw:: html

   <td>

Electrical voltage measurement.Units: volts (V)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

current

.. raw:: html

   </th>

.. raw:: html

   <td>

Ammeter

.. raw:: html

   </td>

.. raw:: html

   <td>

Electrical intensity measurement.Units amps (A)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

frequency

.. raw:: html

   </th>

.. raw:: html

   <td>

Frequencymeter

.. raw:: html

   </td>

.. raw:: html

   <td>

Electrical frequency measurement.Units: herzs (Hz)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

active_power

.. raw:: html

   </th>

.. raw:: html

   <td>

Active power

.. raw:: html

   </td>

.. raw:: html

   <td>

Active power measurement.Units: kilowatts (kW)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

reactive_power

.. raw:: html

   </th>

.. raw:: html

   <td>

Reactive power

.. raw:: html

   </td>

.. raw:: html

   <td>

Reactive power measurement.Units: reactive kilovoltiamperis (kvar)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

cosphi

.. raw:: html

   </th>

.. raw:: html

   <td>

Power factor

.. raw:: html

   </td>

.. raw:: html

   <td>

Sensor that relates the active and reactive power. No units

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

active_energy

.. raw:: html

   </th>

.. raw:: html

   <td>

Active electrical energy meter

.. raw:: html

   </td>

.. raw:: html

   <td>

Measurement of accumulated active power.Units: kWh.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

reactive_energy

.. raw:: html

   </th>

.. raw:: html

   <td>

Reactive electrical energy meter

.. raw:: html

   </td>

.. raw:: html

   <td>

Measurement of accumulated reactive power.Units: kvarh.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

gas_volume

.. raw:: html

   </th>

.. raw:: html

   <td>

Gas meter

.. raw:: html

   </td>

.. raw:: html

   <td>

Measurement of accumulated gas consumption.Units: m3 o Nm3

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

water_meter

.. raw:: html

   </th>

.. raw:: html

   <td>

Water meter

.. raw:: html

   </td>

.. raw:: html

   <td>

Measurement of accumulated water consumption.Units: m3 o l

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

global_solar_irradiance

.. raw:: html

   </th>

.. raw:: html

   <td>

Global solar irradiance

.. raw:: html

   </td>

.. raw:: html

   <td>

Mesurement of solar irradiance

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

leaf_moisture

.. raw:: html

   </th>

.. raw:: html

   <td>

Leaf moisture

.. raw:: html

   </td>

.. raw:: html

   <td>

Leaf wetness

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

oxygen

.. raw:: html

   </th>

.. raw:: html

   <td>

Oxygen

.. raw:: html

   </td>

.. raw:: html

   <td>

O2

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

vertical_level

.. raw:: html

   </th>

.. raw:: html

   <td>

Vertical level

.. raw:: html

   </td>

.. raw:: html

   <td>

Vertical liquid level (water)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

bend

.. raw:: html

   </th>

.. raw:: html

   <td>

Bend

.. raw:: html

   </td>

.. raw:: html

   <td>

Bend

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

lpg

.. raw:: html

   </th>

.. raw:: html

   <td>

Lpg

.. raw:: html

   </td>

.. raw:: html

   <td>

Liquified petroleum gases (H2, CH4, ethanol & isobutane)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

crack_detection

.. raw:: html

   </th>

.. raw:: html

   <td>

Crack detection

.. raw:: html

   </td>

.. raw:: html

   <td>

Crack detection gauge

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

solar_radiation

.. raw:: html

   </th>

.. raw:: html

   <td>

Solar radiation

.. raw:: html

   </td>

.. raw:: html

   <td>

Solar radiation

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

voc

.. raw:: html

   </th>

.. raw:: html

   <td>

Voc

.. raw:: html

   </td>

.. raw:: html

   <td>

Volatile Organic Compounds

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

chloride_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Chloride ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion Cl-

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

temperature

.. raw:: html

   </th>

.. raw:: html

   <td>

Temperature

.. raw:: html

   </td>

.. raw:: html

   <td>

Soil/Water temperature

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

magnessium_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Magnessium ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion Mg2+

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

distance

.. raw:: html

   </th>

.. raw:: html

   <td>

Distance

.. raw:: html

   </td>

.. raw:: html

   <td>

Distance (by metalic pressure or by pressure)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

conductivity

.. raw:: html

   </th>

.. raw:: html

   <td>

Conductivity

.. raw:: html

   </td>

.. raw:: html

   <td>

Conductivity

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

liquid_leakage_line

.. raw:: html

   </th>

.. raw:: html

   <td>

Liquid leakage line

.. raw:: html

   </td>

.. raw:: html

   <td>

Water Leakage / Liquid Detection (Line)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

crack_propagation

.. raw:: html

   </th>

.. raw:: html

   <td>

Crack propagation

.. raw:: html

   </td>

.. raw:: html

   <td>

Crack propagation gauge

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

nitrate_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Nitrate ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion NO3

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

hall_effect

.. raw:: html

   </th>

.. raw:: html

   <td>

Hall effect

.. raw:: html

   </td>

.. raw:: html

   <td>

Hall effect

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

vibration

.. raw:: html

   </th>

.. raw:: html

   <td>

Vibration

.. raw:: html

   </td>

.. raw:: html

   <td>

Vibration (lamina)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

copper_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Copper ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion Cu2+

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

calcium_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Calcium ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion Ca+

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

dendometer

.. raw:: html

   </th>

.. raw:: html

   <td>

Dendometer

.. raw:: html

   </td>

.. raw:: html

   <td>

Trunk, stem or fruit diameter

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

iodide_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Iodide ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion I-

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

bromide_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Bromide ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion Br-

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

sodium_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Sodium ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion Na+

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

linear_displacement

.. raw:: html

   </th>

.. raw:: html

   <td>

Linear displacement

.. raw:: html

   </td>

.. raw:: html

   <td>

Linear displacement

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

atmospheric_pressure

.. raw:: html

   </th>

.. raw:: html

   <td>

Atmospheric pressure

.. raw:: html

   </td>

.. raw:: html

   <td>

Atmospheric pressure

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

methane

.. raw:: html

   </th>

.. raw:: html

   <td>

Methane

.. raw:: html

   </td>

.. raw:: html

   <td>

CH4

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

pressure

.. raw:: html

   </th>

.. raw:: html

   <td>

Pressure

.. raw:: html

   </td>

.. raw:: html

   <td>

Pressure/ Weight

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

ammonia

.. raw:: html

   </th>

.. raw:: html

   <td>

Ammonia

.. raw:: html

   </td>

.. raw:: html

   <td>

NH3

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

redox_potential

.. raw:: html

   </th>

.. raw:: html

   <td>

Redox potential

.. raw:: html

   </td>

.. raw:: html

   <td>

Oxidation Reduction Potential

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

proximity_indoor

.. raw:: html

   </th>

.. raw:: html

   <td>

Proximity indoor

.. raw:: html

   </td>

.. raw:: html

   <td>

Ultrasound (indoor)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

air_pollutant

.. raw:: html

   </th>

.. raw:: html

   <td>

Air pollutant

.. raw:: html

   </td>

.. raw:: html

   <td>

Air pollutants-I (NH3, SH2, ethanol and toluene) and air pollutants-II
(H2, CH4, CO, ethanol and isobutane)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

liquid_leakage_point

.. raw:: html

   </th>

.. raw:: html

   <td>

Liquid leakage point

.. raw:: html

   </td>

.. raw:: html

   <td>

Water Leakage / Liquid Detection (Point)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

proximity_outdoor

.. raw:: html

   </th>

.. raw:: html

   <td>

Proximity outdoor

.. raw:: html

   </td>

.. raw:: html

   <td>

Ultrasound (outdoor IP67)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

potassium_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Potassium ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion K+

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

o_saturation

.. raw:: html

   </th>

.. raw:: html

   <td>

O saturation

.. raw:: html

   </td>

.. raw:: html

   <td>

Dissolved Oxygen

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

presence

.. raw:: html

   </th>

.. raw:: html

   <td>

Presence

.. raw:: html

   </td>

.. raw:: html

   <td>

Presence (PIR)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

stretch

.. raw:: html

   </th>

.. raw:: html

   <td>

Stretch

.. raw:: html

   </td>

.. raw:: html

   <td>

Stretch

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

liquid_level

.. raw:: html

   </th>

.. raw:: html

   <td>

Liquid level

.. raw:: html

   </td>

.. raw:: html

   <td>

Horizontal liquid level (combustibles or water)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

load

.. raw:: html

   </th>

.. raw:: html

   <td>

Load

.. raw:: html

   </td>

.. raw:: html

   <td>

Load

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

fluoride_ion

.. raw:: html

   </th>

.. raw:: html

   <td>

Fluoride ion

.. raw:: html

   </td>

.. raw:: html

   <td>

Ion F-

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

ph

.. raw:: html

   </th>

.. raw:: html

   <td>

Ph

.. raw:: html

   </td>

.. raw:: html

   <td>

pH

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

solvent_vapors

.. raw:: html

   </th>

.. raw:: html

   <td>

Solvent vapors

.. raw:: html

   </td>

.. raw:: html

   <td>

Solvent vapors (H2, CH4, CO, ethanol and isobutane)

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <th>

accelerometer

.. raw:: html

   </th>

.. raw:: html

   <td>

Accelerometer

.. raw:: html

   </td>

.. raw:: html

   <td>

Accelerometer

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>
