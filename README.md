# rsc-2019-weather-station

## Components

### Weather station

[SparkFun Electronics SEN-08942](https://www.digikey.de/product-detail/de/sparkfun-electronics/SEN-08942/1568-1555-ND/5684383)

[Data sheet](https://www.sparkfun.com/datasheets/Sensors/Weather/Weather%20Sensor%20Assembly..pdf)

### Wifi Adapter

[Alfa Network AWUS036NHA](https://www.amazon.de/dp/B01D064VMS/ref=cm_sw_r_cp_apa_i_2wD4Bb07P9566)

### Wifi Adapter Bracket

You will need 2 M3 screws with min. 15mm length and two nuts

#### Side 1

[Wifi_Adapter_Bracket_20mm_Side_1.stl](wifi-adapter-bracket/Wifi_Adapter_Bracket_20mm_Side_1.stl)

#### Side 2

[Wifi_Adapter_Bracket_20mm_Side_2.stl](wifi-adapter-bracket/Wifi_Adapter_Bracket_20mm_Side_2.stl)

## Requirements

### [pip](https://pypi.org/project/pip/)

- `sudo apt-get install python-pip`

### [pipenv](https://github.com/pypa/pipenv)

- `pip install --user pipenv`
- Add pipenv to your path `echo -e '\nexport PATH="$PATH:~/.local/bin"' >> ~/.bashrc`
- Activate `source ~/.bashrc`

### [mosquitto](https://mosquitto.org/)

- Install mosquitto with `sudo apt-get install -y mosquitto mosquitto-clients`

## Installation

- Clone the repository with `git clone https://github.com/D3473R/rsc-2019-weather-station.git`
- Navigate in the cloned directory with `cd rsc-2019-weather-station`
- Install the python dependencies with `pipenv install`

## Run

- Start a pipenv shell with `pipenv shell`
- Run `weather.py` with `python src/weather.py`

To receive the data on another machine you can use any MQTT Client, e.g. [mqttfx](https://mqttfx.jensd.de/).

Simply connect to the ip of the raspberry and subscribe to the channel `weather`

To receive the data in python you can also use [paho-mqtt](https://pypi.org/project/paho-mqtt/)

## Configuration

You can disable the visualisation of the data if you set `ENABLE_GUI = False` in `weather.py`

## Data

A json paket consists of the timestamp the paket was sent, the wind direction in degrees (in 16 steps) and the wind speed in m/s.

`{"timestamp": "2019-02-13T15:01:13Z", "direction": 67.5, "speed": 4.32}`

## Demo

[![asciicast](https://asciinema.org/a/223777.svg)](https://asciinema.org/a/223777)
