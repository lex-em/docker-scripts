# Postgres monitoring dashboard

### postgres_exporter

Compose configuration uses `postgres` host name of database in `DATA_SOURCE_NAME` variable, change it as you needed (login/password too)

If you have postgres running under docker at the same machine - you can make network external (database service name is a host (`postgres`)):
```yaml
networks:
  default:
    external:
      name: postgres_default # postgres container network name
```

Additional metrics are placed at `postgres_exporter/metrics.yml`

### node-exporter

It just works, no additional settings needed :)

### prometheus

Prometheus configuration placed at `prometheus/prometheus.yml`. All target hosts are docker service names

### grafana

At first need to add prometheus datasource: 
* Left vertical menu -> Configuration -> Data Sources
* Add datasource of type prometheus
  * name (in lower case!): prometheus 
  * url: http://prometheus:9090)

### System dashboard

Recommended for use dashboard for node-exporter [#1860](https://grafana.com/grafana/dashboards/1860)

Install:

At first need to add prometheus datasource: 
* Left vertical menu -> Create -> Import
* Put number into `Grafana.com Dashboard` input

### Postgres dashboard

Postgres dashboard should be imported from `grafana-pg-dashboard.json` (uses postgres_exporter custom metrics):
* Left vertical menu -> Create -> Import
* Put json content into input or choose file via `Uplaod .json file` button.