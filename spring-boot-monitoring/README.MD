# Spring boot monitoring

### prometheus

Prometheus configuration placed at `prometheus/prometheus.yml`. All target hosts are docker service names.
Data folder `prometheus/data` is mounted into container and store prometheus database.

Additional container `volumes-provisioner` is used for modifying data folder rights.

### grafana

Datasource (prometheus) and dashboards are configured statically.
Dashboards:

- Spring Boot 2.1 Statistics [#10280](https://grafana.com/grafana/dashboards/10280)
