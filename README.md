# panograf
A TIG stack for monitoring Palo Alto Networks firewalls.

## Overview
This `docker-compose.yml` file implements a TIG stack ([Telegraf](https://www.influxdata.com/time-series-platform/telegraf/), [InfluxDB](https://www.influxdata.com/products/influxdb/), and [Grafana](https://grafana.com)) used for monitoring Palo Alto Networks NGFW devices via SNMP and trending the results in a Grafana dashboard.

## Prerequisites
* One or more [Palo Alto Networks NGFW](https://www.paloaltonetworks.com/network-security/next-generation-firewall) devices running PAN-OS 10.0 or greater
* [Docker](https://docs.docker.com/get-docker/) engine 20.10.6 or greater

## Installation

1. Clone this repository onto a Docker server and then `cd` into the repository directory.
2. Edit the file `telegraf/config/panos.conf` and add a list of firewall IP addresses to monitor in the section `[inputs.snmp]` and define the SNMP community string that will be used.
3. Ensure that SNMP is enabled on your firewall management interfaces and that an SNMP community string is defined and matches the one in the configuration file.
4. Run the command `docker-compose up -d` to start the deployment.
5. Access the Grafana server at [http://localhost:3000](http://localhost:3000).
6. Log into the Grafana server (admin/admin) and access the PAN-OS dashboard at *Dashboards > Manage > Network > Palo Alto Networks Firewalls*.

## Credits
* Thanks to Victor Brahana ([vbarahona](https://github.com/vbarahona))for the Grafana dashboard and telegraf configs located at [https://github.com/vbarahona/Panos2Grafana](https://github.com/vbarahona/Panos2Grafana) and distributed on [Grafana Labs](https://grafana.com/grafana/dashboards/11321).