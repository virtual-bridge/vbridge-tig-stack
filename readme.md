# vBridge TIG Stack

TIG stack is short for Telegraf, InfluxData, Grafana. This is a base compose configuration for standing up this environment automatically and having telegraf configration set to poll vsphere environments and the base vsphere overview templates presented.

Special thanks to Jorge del la Cruz for the [polling interval](https://jorgedelacruz.uk/2020/01/23/vmware-how-to-achieve-a-perfect-metric-collection-interval-with-telegraf-influxdb-and-grafana/) detail and the grafana [vSphere overview templates](https://grafana.com/grafana/dashboards/8159).

## Requirements

- You will need a docker host with compose installed
- Clone this repository

## Configuration
- Update the configuration.env file as required with your desired credentials for the influxdb and grafana
- Edit the telegraf/etc/telegraf.conf file to have your vsphere location(s) and access credentials (under [[inputs.vsphere]], note: there are 2 different pollers so set both)

## Usage

```bash
docker-compose up -d
```

Will load the environment up as a daemon. 

You can then hit http://yourhost:3000 in your browser.