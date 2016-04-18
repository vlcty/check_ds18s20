check_ds18s20
=============

Monitor DS18S20 temperature sensors

This script for your monitoring system queries a DS18S20 temperature sensor via
a 1-wire bus. It will print out the temperature in a human readable format and
also nice performance data for graphing.

Note: This script is just for gathering perforamance data. You can't monitor
if the temperature is below or above a specific temperature.

Usage:
------

The script takes ```--device``` as only argument. Sample call:

```bash
:~$ /usr/lib/nagios/plugins/check_DS18S20 --device="10-0008030b1ab6"
OK - Temp: 28.812 °C|temp=28.812
```

If the sensor is not found it'll print a nice error message:

```
:~$ /usr/lib/nagios/plugins/check_DS18S20 --device="10-0008030ab835"
CRITICAL - No DS18S20 found under /sys/bus/w1/devices/10-0008030ab835/w1_slave
```

Usage for Icinga 2
------------------

The needed CheckCommand can be found under ```icinga2-CheckCommand.conf```. The
rest of the configuration is just like for every other check.
