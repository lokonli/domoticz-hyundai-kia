# Domoticz Hyundai-Kia plugin
Author: Creasol https://www.creasol.it/domotics

For any support request, please write email to linux@creasol.it or enter the Telegram DomBus group https://t.me/DomBus 


# Introduction

This plugin is designed for [Domoticz](https://www.domoticz.com) home automation system and provide a way to get status from Hyunday and Kia cars.

It's based on the [hyundai-kia-connect-api](https://pypi.org/project/hyundai-kia-connect-api/) python library, written by Fuat Akgun.  

In this folder you can find the python plugin for Domoticz: **you can install the hardware plugin by using Python Plugin Manager, or typing the following commands from the linux shell**:

# Installation

```bash
#become root user
sudo su -

#install git, if not already installed
which git
if [ $? -ne 0 ]; then sudo apt install git; fi

#change to the domoticz directory / plugins
cd /home/pi/domoticz/plugins 

#fetch the Python Plugin Manager (that can be used to install/upgrade other plugins, including domoticz-hyundai-kia)
git clone https://github.com/ycahome/pp-manager

#fetch Creasol Plugin
git clone https://github.com/CreasolTech/domoticz-hyundai-kia

#install hyundai-kia-connect-api lib
pip3 install hyundai-kia-connect-api

#restart Domoticz daemon
service domoticz restart
```

# Charging the electric car in a smart way

Creasol is developing a __cheap and smart DIY EVSE module__ that can work stand-alone or connected to Domoticz.

Features:
* detects plug connection and disconnection
* detects when the electric vehicle starts and stops charging
* detects alarms from vehicle
* interfaces a bidirectional energy meter to know the real time import or export power from grid
* operates as __stand-alone__ (no need for a domotic controller) with the possibility to select two charging mode:
    1. __use the maximum power allowed by electricity meter__, preventing overloads and disconnections
    2. __use only renewable energy (keep import power around 0W)__

* operates in a __controlled mode, with Domoticz__ home automation system: in this case it's possible to 
	1. easily set the __minimum and maximum battery level__
	2. easily set the __maximum charging current__
	3. __when battery level is below minimum, charge at the max power__ permitted by the electricity meter (in Italy, alternates 90 minutes at maximum power + 27% and 90 minutes at maximum power + 10%, ___it's not possible to charge faster!___ The electrical system must be checked carefully when using maximum power, to avoid overheating and fires!!)
	4. __when battery level is between minimum and maximum, charge using only power from renewable energy from photovoltaic__

More info at https://www.creasol.it/en/support/domotics-home-automation-and-diy/155-smart-electric-vehicle-charging

