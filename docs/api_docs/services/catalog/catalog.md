Catalog
=======

## Description

The catalog service allows to register or modify your own sensors/components or query the characteristics of a sensor or provider.

All requests for this service will have the following format:

```
 http://<your_api_server.com>/catalog/<provider_id>
```

where <em>provider_id</em> is optional and should be included depending on the operation.

## Actions

The available actions for this service are:

* [Adding components / sensors](./create_sensors.html)
* [Update data components / sensors](./update_sensors.html)
* [Retrieve list of providers / sensors](./retrieve_authorized_entities.html)
* [Remove components / sensors](./delete_component_or_sensor.html)

## Component types

The list of component types should be configured for each Sentilo instance, the following list could be used as a reference for any city:

<table>
	<tbody>
		<tr>
			<th>Id</th>
			<th>Name</th>
			<th>Description</th>
		</tr>
		<tr>
			<th>temperature</th>
			<td>Temperature</td>
			<td>Temperature measurement</td>
		</tr>
		<tr>
			<th>noise</th>
			<td>Soundmeter</td>
			<td>Sound measurement</td>
		</tr>
		<tr>
			<th>wind</th>
			<td>Anemometer</td>
			<td>Wind speed</td>
		</tr>
		<tr>
			<th>humidity</th>
			<td>Humidity</td>
			<td>Humidity measurement</td>
		</tr>
		<tr>
			<th>air_quality</th>
			<td>Air Quality</td>
			<td>Air Quality control</td>
		</tr>
		<tr>
			<th>water_quality</th>
			<td>Water Quality</td>
			<td>Water Quality control</td>
		</tr>
		<tr>
			<th>meteo</th>
			<td>Meteorology</td>
			<td>Weather Station</td>
		</tr>
		<tr>
			<th>parking</th>
			<td>Occupation parking</td>
			<td>Parking control</td>
		</tr>
		<tr>
			<th>luminosity</th>
			<td>Luminosity</td>
			<td>Luminosity measurement</td>
		</tr>
		<tr>
			<th>glass_container</th>
			<td>Occupancy container level</td>
			<td>Glass occupancy container measurement</td>
		</tr>
		<tr>
			<th>paper_container</th>
			<td>Occupancy container level</td>
			<td>Paper occupancy container measurement</td>
		</tr>
		<tr>
			<th>plastic_container</th>
			<td>Occupancy container level</td>
			<td>Plastic occupancy container measurement</td>
		</tr>
		<tr>
			<th>organic_container</th>
			<td>Occupancy container level</td>
			<td>Organic occupancy container measurement</td>
		</tr>
		<tr>
			<th>refuse_container</th>
			<td>Occupancy container level</td>
			<td>Refuse occupancy container measurement</td>
		</tr>
		<tr>
			<th>container_volum</th>
			<td>Occupancy container level</td>
			<td>Generic occupancy container measurement</td>
		</tr>
		<tr>
			<th>soil_moisture</th>
			<td>Soil moisture</td>
			<td>Soil moisture measurement</td>
		</tr>
		<tr>
			<th>park_meter</th>
			<td>Parking meter</td>
			<td>Parking meter control</td>
		</tr>
		<tr>
			<th>traffic</th>
			<td>Traffic</td>
			<td>Traffic measurement</td>
		</tr>
		<tr>
			<th>people_flow</th>
			<td>People flow</td>
			<td>Pedestrian flow measurement</td>
		</tr>
		<tr>
			<th>flowmeter</th>
			<td>Water flow</td>
			<td>Water flow measurement</td>
		</tr>
		<tr>
			<th>solenoid_valve</th>
			<td>Electrovalve</td>
			<td>Solenoid control</td>
		</tr>
		<tr>
			<th>salinity</th>
			<td>Salinity</td>
			<td>Soil salinity measurement</td>
		</tr>
		<tr>
			<th>internal_ambient_conditions</th>
			<td>Internal Environmental Conditions</td>
			<td>Temperature, humidity and luminosity measurement</td>
		</tr>
		<tr>
			<th>external_ambient_conditions</th>
			<td>External environmental conditions</td>
			<td>Temperature, humidity and luminosity measurement</td>
		</tr>
		<tr>
			<th>network_analyzer</th>
			<td>Network analyzer</td>
			<td>Electric network analyzer</td>
		</tr>
		<tr>
			<th>gas_meter</th>
			<td>Gas meter</td>
			<td>Gas consumption meter</td>
		</tr>
		<tr>
			<th>electricity_meter</th>
			<td>Electricity meter</td>
			<td>Electricity consumption meter</td>
		</tr>
		<tr>
			<th>water_meter</th>
			<td>Water meter</td>
			<td>Water consumption meter</td>
		</tr>
		<tr>
			<th>soil_sensor</th>
			<td>Soil sensor</td>
			<td>Soil mesurement of salinity, mosture, etc</td>
		</tr>
		<tr>
			<th>generic</th>
			<td>Generic component type</td>
			<td>Default component type if not specified</td>
		</tr>
		<tr>
			<th>plugsense</th>
			<td>Plug &amp; Sense</td>
			<td>Plug &amp; Sense Libelium component</td>
		</tr>
	</tbody>
</table>

## Sensor types

The list of sensor types should be configured for each Sentilo instance, the following list could be used as a reference for any city:


<table>
	<tbody>
		<tr>
			<th>Id</th>
			<th>Name</th>
			<th>Description</th>
		</tr>
		<tr>
			<th>temperature</th>
			<td>Temperature</td>
			<td>Temperature measurement</td>
		</tr>
		<tr>
			<th>noise</th>
			<td>Soundmeter Class II</td>
			<td>Sound level measuring class II.</td>
		</tr>
		<tr>
			<th>noise_class_i</th>
			<td>Soundmeter Class I</td>
			<td>Sound level measuring class I</td>
		</tr>
		<tr>
			<th>anemometer</th>
			<td>Anemometer</td>
			<td>Wind Speed ​measuring</td>
		</tr>
		<tr>
			<th>humidity</th>
			<td>Humidity</td>
			<td>Humidity measuring</td>
		</tr>
		<tr>
			<th>parking</th>
			<td>Occupation parking</td>
			<td>Occupation parking control</td>
		</tr>
		<tr>
			<th>luminosity</th>
			<td>Luminosity</td>
			<td>Luminosity measuring</td>
		</tr>
		<tr>
			<th>container_volum</th>
			<td>Occupancy container level</td>
			<td>Occupancy container measurement</td>
		</tr>
		<tr>
			<th>container_overturn</th>
			<td>Container overturned</td>
			<td>Container overturned indicator</td>
		</tr>
		<tr>
			<th>container_open</th>
			<td>Container open</td>
			<td>Container opening indicator</td>
		</tr>
		<tr>
			<th>status</th>
			<td>Sensor status</td>
			<td>Status control</td>
		</tr>
		<tr>
			<th>battery</th>
			<td>Battery level</td>
			<td>Battery level measurement</td>
		</tr>
		<tr>
			<th>soil_moisture_15</th>
			<td>Soil moisture 15 cm.</td>
			<td>Soil moisture measurement</td>
		</tr>
		<tr>
			<th>soil_moisture_35</th>
			<td>Soil moisture 35 cm.</td>
			<td>Soil moisture measurement</td>
		</tr>
		<tr>
			<th>park_meter</th>
			<td>Parking meter</td>
			<td>Parking meter control</td>
		</tr>
		<tr>
			<th>vehicle_volume</th>
			<td>Number of vehicles</td>
			<td>Measurement of number of vehicles</td>
		</tr>
		<tr>
			<th>vehicle_occupation_average</th>
			<td>Average occupancy</td>
			<td>Measurement of average occupancy in vehicles</td>
		</tr>
		<tr>
			<th>vehicle_speed</th>
			<td>Speed ​​Vehicle</td>
			<td>Vehicle speed ​​measurement</td>
		</tr>
		<tr>
			<th>air_quality_no2</th>
			<td>NO2</td>
			<td>Nitrogen dioxide measurement</td>
		</tr>
		<tr>
			<th>air_quality_pm10</th>
			<td>PM10</td>
			<td>Measurement of suspension particles PM10</td>
		</tr>
		<tr>
			<th>air_quality_pm25</th>
			<td>PM25</td>
			<td>Measurement of supsension particles PM25</td>
		</tr>
		<tr>
			<th>air_quality_o3</th>
			<td>O3</td>
			<td>Ozone measurement</td>
		</tr>
		<tr>
			<th>air_quality_so2</th>
			<td>SO2</td>
			<td>Sulfur dioxide measurement</td>
		</tr>
		<tr>
			<th>air_quality_co</th>
			<td>CO</td>
			<td>Carbon Monoxide measurement</td>
		</tr>
		<tr>
			<th>air_quality_co2</th>
			<td>CO2</td>
			<td>Carbon dioxide measurement</td>
		</tr>
		<tr>
			<th>people_flow</th>
			<td>People flow</td>
			<td>Measurement of pedestrian flow</td>
		</tr>
		<tr>
			<th>flowmeter</th>
			<td>Water flow</td>
			<td>Water flow measurement</td>
		</tr>
		<tr>
			<th>solenoid_valve</th>
			<td>Electrovalve</td>
			<td>Solenoid actuator</td>
		</tr>
		<tr>
			<th>eto</th>
			<td>Evotranspiration</td>
			<td>Evotranspiration measurement</td>
		</tr>
		<tr>
			<th>salinity</th>
			<td>Salinity</td>
			<td>Soil salinity measurement</td>
		</tr>
		<tr>
			<th>pluviometer</th>
			<td>Pluviometer</td>
			<td>Rain measurement</td>
		</tr>
		<tr>
			<th>rain</th>
			<td>Rain gauge</td>
			<td>Rain indicator (it's raining/it's not raining)</td>
		</tr>
		<tr>
			<th>wind</th>
			<td>Wind gauge</td>
			<td>Wind indicator (&gt;X m/s)</td>
		</tr>
		<tr>
			<th>wind_direction_6_m</th>
			<td>Wind direction</td>
			<td>Wind direction at 6 meters</td>
		</tr>
		<tr>
			<th>wind_direction_10_m</th>
			<td>Wind direction</td>
			<td>Wind direction at 10 meters</td>
		</tr>
		<tr>
			<th>voltage</th>
			<td>Voltmetre</td>
			<td>Electrical voltage measurement.<br>Units: volts (V)
			</td>
		</tr>
		<tr>
			<th>current</th>
			<td>Ammeter</td>
			<td>Electrical intensity measurement.<br>Units amps (A)
			</td>
		</tr>
		<tr>
			<th>frequency</th>
			<td>Frequencymeter</td>
			<td>Electrical frequency measurement.<br>Units: herzs (Hz)
			</td>
		</tr>
		<tr>
			<th>active_power</th>
			<td>Active power</td>
			<td>Active power measurement.<br>Units: kilowatts (kW)
			</td>
		</tr>
		<tr>
			<th>reactive_power</th>
			<td>Reactive power</td>
			<td>Reactive power measurement.<br>Units: reactive kilovoltiamperis (kvar)
			</td>
		</tr>
		<tr>
			<th>cosphi</th>
			<td>Power factor</td>
			<td>Sensor that relates the active and reactive power. No units</td>
		</tr>
		<tr>
			<th>active_energy</th>
			<td>Active electrical energy meter</td>
			<td>Measurement of accumulated active power.<br>Units: kWh.</td>
		</tr>
		<tr>
			<th>reactive_energy</th>
			<td>Reactive electrical energy meter</td>
			<td>Measurement of accumulated reactive power.<br>Units: kvarh.</td>
		</tr>
		<tr>
			<th>gas_volume</th>
			<td>Gas meter</td>
			<td>Measurement of accumulated gas consumption.<br>Units: m3 o Nm3</td>
		</tr>
		<tr>
			<th>water_meter</th>
			<td>Water meter</td>
			<td>Measurement of accumulated water consumption.<br>Units: m3 o l</td>
		</tr>
		<tr>
			<th>global_solar_irradiance</th>
			<td>Global solar irradiance</td>
			<td>Mesurement of solar irradiance</td>
		</tr>
		<tr>
			<th>leaf_moisture</th>
			<td>Leaf moisture</td>
			<td>Leaf wetness</td>
		</tr>
		<tr>
			<th>oxygen</th>
			<td>Oxygen</td>
			<td>O2</td>
		</tr>
		<tr>
			<th>vertical_level</th>
			<td>Vertical level</td>
			<td>Vertical liquid level (water)</td>
		</tr>
		<tr>
			<th>bend</th>
			<td>Bend</td>
			<td>Bend</td>
		</tr>
		<tr>
			<th>lpg</th>
			<td>Lpg</td>
			<td>Liquified petroleum gases (H2, CH4, ethanol &amp; isobutane)</td>
		</tr>
		<tr>
			<th>crack_detection</th>
			<td>Crack detection</td>
			<td>Crack detection gauge</td>
		</tr>
		<tr>
			<th>solar_radiation</th>
			<td>Solar radiation</td>
			<td>Solar radiation</td>
		</tr>
		<tr>
			<th>voc</th>
			<td>Voc</td>
			<td>Volatile Organic Compounds</td>
		</tr>
		<tr>
			<th>chloride_ion</th>
			<td>Chloride ion</td>
			<td>Ion Cl-</td>
		</tr>
		<tr>
			<th>temperature</th>
			<td>Temperature</td>
			<td>Soil/Water temperature</td>
		</tr>
		<tr>
			<th>magnessium_ion</th>
			<td>Magnessium ion</td>
			<td>Ion Mg2+</td>
		</tr>
		<tr>
			<th>distance</th>
			<td>Distance</td>
			<td>Distance (by metalic pressure or by pressure)</td>
		</tr>
		<tr>
			<th>conductivity</th>
			<td>Conductivity</td>
			<td>Conductivity</td>
		</tr>
		<tr>
			<th>liquid_leakage_line</th>
			<td>Liquid leakage line</td>
			<td>Water Leakage / Liquid Detection (Line)</td>
		</tr>
		<tr>
			<th>crack_propagation</th>
			<td>Crack propagation</td>
			<td>Crack propagation gauge</td>
		</tr>
		<tr>
			<th>nitrate_ion</th>
			<td>Nitrate ion</td>
			<td>Ion NO3</td>
		</tr>
		<tr>
			<th>hall_effect</th>
			<td>Hall effect</td>
			<td>Hall effect</td>
		</tr>
		<tr>
			<th>vibration</th>
			<td>Vibration</td>
			<td>Vibration (lamina)</td>
		</tr>
		<tr>
			<th>copper_ion</th>
			<td>Copper ion</td>
			<td>Ion Cu2+</td>
		</tr>
		<tr>
			<th>calcium_ion</th>
			<td>Calcium ion</td>
			<td>Ion Ca+</td>
		</tr>
		<tr>
			<th>dendometer</th>
			<td>Dendometer</td>
			<td>Trunk, stem or fruit diameter</td>
		</tr>
		<tr>
			<th>iodide_ion</th>
			<td>Iodide ion</td>
			<td>Ion I-</td>
		</tr>
		<tr>
			<th>bromide_ion</th>
			<td>Bromide ion</td>
			<td>Ion Br-</td>
		</tr>
		<tr>
			<th>sodium_ion</th>
			<td>Sodium ion</td>
			<td>Ion Na+</td>
		</tr>
		<tr>
			<th>linear_displacement</th>
			<td>Linear displacement</td>
			<td>Linear displacement</td>
		</tr>
		<tr>
			<th>atmospheric_pressure</th>
			<td>Atmospheric pressure</td>
			<td>Atmospheric pressure</td>
		</tr>
		<tr>
			<th>methane</th>
			<td>Methane</td>
			<td>CH4</td>
		</tr>
		<tr>
			<th>pressure</th>
			<td>Pressure</td>
			<td>Pressure/ Weight</td>
		</tr>
		<tr>
			<th>ammonia</th>
			<td>Ammonia</td>
			<td>NH3</td>
		</tr>
		<tr>
			<th>redox_potential</th>
			<td>Redox potential</td>
			<td>Oxidation Reduction Potential</td>
		</tr>
		<tr>
			<th>proximity_indoor</th>
			<td>Proximity indoor</td>
			<td>Ultrasound (indoor)</td>
		</tr>
		<tr>
			<th>air_pollutant</th>
			<td>Air pollutant</td>
			<td>Air pollutants-I (NH3, SH2, ethanol and toluene) and air
				pollutants-II (H2, CH4, CO, ethanol and isobutane)</td>
		</tr>
		<tr>
			<th>liquid_leakage_point</th>
			<td>Liquid leakage point</td>
			<td>Water Leakage / Liquid Detection (Point)</td>
		</tr>
		<tr>
			<th>proximity_outdoor</th>
			<td>Proximity outdoor</td>
			<td>Ultrasound (outdoor IP67)</td>
		</tr>
		<tr>
			<th>potassium_ion</th>
			<td>Potassium ion</td>
			<td>Ion K+</td>
		</tr>
		<tr>
			<th>o_saturation</th>
			<td>O saturation</td>
			<td>Dissolved Oxygen</td>
		</tr>
		<tr>
			<th>presence</th>
			<td>Presence</td>
			<td>Presence (PIR)</td>
		</tr>
		<tr>
			<th>stretch</th>
			<td>Stretch</td>
			<td>Stretch</td>
		</tr>
		<tr>
			<th>liquid_level</th>
			<td>Liquid level</td>
			<td>Horizontal liquid level (combustibles or water)</td>
		</tr>
		<tr>
			<th>load</th>
			<td>Load</td>
			<td>Load</td>
		</tr>
		<tr>
			<th>fluoride_ion</th>
			<td>Fluoride ion</td>
			<td>Ion F-</td>
		</tr>
		<tr>
			<th>ph</th>
			<td>Ph</td>
			<td>pH</td>
		</tr>
		<tr>
			<th>solvent_vapors</th>
			<td>Solvent vapors</td>
			<td>Solvent vapors (H2, CH4, CO, ethanol and isobutane)</td>
		</tr>
		<tr>
			<th>accelerometer</th>
			<td>Accelerometer</td>
			<td>Accelerometer</td>
		</tr>
	</tbody>
</table>
