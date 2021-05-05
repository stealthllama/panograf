# panograf
A TIG stack for monitoring Palo Alto Networks firewalls.

## Overview
This `docker-compose.yml` file implements a TIG stack ([Telegraf](https://www.influxdata.com/time-series-platform/telegraf/), [InfluxDB](https://www.influxdata.com/products/influxdb/), [Grafana](https://grafana.com)) used for monitoring Palo Alto Networks NGFW devices.

## Installation

1. Edit the file `telegraf/config/panos.conf` and add a list of firewall IP addresses to monitor in the section `[inputs.snmp]` and define the SNMP community string that will be used.
2. Ensure that SNMP is enabled on your firewall management interfaces and that an SNMP community string is defined and matches the one in the configuration file.
3. Run the command `docker-compose up -d` to start the deployment.
4. Access the Grafana server at [http://localhost:3000](http://localhost:3000).
5. Log into the Grafana server (admin/admin) and access the PAN-OS dashboard.