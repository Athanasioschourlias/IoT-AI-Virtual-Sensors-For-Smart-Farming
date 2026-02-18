
# Virtual sensors for smart farming: An IoT- and AI-enabled approach

This repository contains the datasets and supporting files associated with the following publication:

> **Virtual sensors for smart farming: An IoT- and AI-enabled approach**  
> Authors: Athanasios Chourlias, John Violos, Aris Leivadeas
> Journal: Internet of Things, 2025
> Published via ScienceDirect  
> Article link: https://www.sciencedirect.com/science/article/pii/S2542660525001258?via%3Dihub  
> DOI: https://doi.org/10.1016/j.iot.2025.101611


## 📝 Abstract

Smart farming relies on precise environmental data to optimize agricultural practices, with keymetrics such as air temperature, humidity, rain, ambient light, ultraviolet (UV) radiation andsoil moisture to play a crucial role in agricultural decision-making. However, the vast spatialcoverage of agricultural fields and the high cost of deploying numerous physical sensors posesignificant challenges, particularly for small and medium-sized farms. To address these issues,virtual sensors – machine learning models that predict sensor values based on data from relevantphysical sensors – offer a cost-effective and scalable alternative. In this research, a number ofArduino-based IoT devices are designed and deployed equipped with various physical sensors,a lithium-polymer battery which recharges continuously using a 6 W waveshare solar panel,and a Real-Time Clock (RTC) module that synchronizes data logging. The IoT devices operatedacross two agricultural fields over a span of almost three months. The data collected form thebasis for evaluating multiple machine learning models as virtual sensors. Furthermore, the useof open weather data to develop a hardware-free solution is explored. Experimental results showthat virtual sensors provide a cost-effective and accurate method for replacing physical sensors.The Light Gradient Boosting Machine emerged as the most accurate model for virtual sensors,achieving prediction errors of less than 1% in most of the cases. This makes it a valuable toolfor enabling cost-effective and data-driven farming in resource-constrained IoT devices.


## 📂 Folder Description

### 📊 `Datasets/`

Contains all datasets used in the study.

Each subfolder corresponds to a monitoring station:

- `Station_1/` – Raw Data collected from Station 1, annotated with information from external sensors & Irrigation status.`
- `Station_2/` – Raw Data collected from Station 2, annotated with information from external sensors & Irrigation status.
- `Station_3/` – Raw Data collected from Station 3, annotated with information from external sensors & Irrigation status.
- `Station_4/` – Raw Data collected from Station 4, annotated with information from external sensors & Irrigation status.

> [!NOTE] 
> As mentioned, we did not manage to retrieve any data from station 5


#### 📊 Dataset Variables

Each dataset inside the `datasets/Station_X/` folders contains the following columns:

| Column Name | Description | Unit | Notes |
|-------------|------------|------|-------|
| `Timestamp` | Date and time of measurement | Unix Timestamp | elapsed since 00:00:00 UTC on 1 January 1970 |
| `Temperature(C)` | Ambient air temperature | °C | Measured by FRobot DHT22 temperature & Humidity sensor |
| `Humidity(%)` | Relative humidity | % | 0–100% Value from FRobot DHT22 temperature & Humidity sensor |
| `Rain_raw` | Raw rain sensor reading | ADC Value | - |
| `Light_raw` | Ambient Light | LUX | ALS Spectral Response Wavelength: 450nm to 700nm. Sensor possisioned without any abstructions to the sky. Sensor comes pre-calibrated from DFROBOT.|
| `soil_moist_percent(%)` | Soil Moisture as a percentage | % | Calculated using Min-Max method from 'soil_moist_raw' |
| `UV_raw` | Raw UV sensor reading | ADC Value | Unprocessed UV measurement from sensor possisioned without any abstructions to the sky. Sensor comes pre-calibrated from DFROBOT. |
| `irrigation` | Irrigation system status | Binary (0/1) | 1 = Irrigation system is active, 0 = No Irrigation |
| `artificial_water_consumption_per_acre(L/3min)` | Water applied per acre during 3-minute interval | Liters / 3 minutes | Added during annotation based on irrigation system average readings & total field acres |
| `total_artificial_water_consumption(L/3min)` | Total water consumption during 3-minute interval | Liters / 3 minutes | Added during annotation based on irrigation system average readings |
| `soil_moist_raw` | Raw soil moisture sensor reading | ADC value | Calibrated with relative soil-moisture humidity of 11% |

---

### 💻 `3D Models/`

Contains all models created for the assembly of each station:

- `weather_station/` – Weather station waterproof sensor enclosure.
- `case_misc/` – In this folder there are two models for two different types of electrical junction boxes. Both types very commonly used.

---

### 💻 `Images/`

Contains all scripts and notebooks used for:

- `hardware/` – Photos from the assebly and deployment of the stations
