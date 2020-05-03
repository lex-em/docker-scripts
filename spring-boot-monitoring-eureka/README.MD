# Spring boot monitoring

### prometheus

Prometheus configuration placed at `prometheus/prometheus.yml`. All target hosts are docker service names.
Data folder `prometheus/data` is mounted into container and store prometheus database.

Additional container `volumes-provisioner` is used for modifying data folder rights.

### grafana

Datasource (prometheus) and dashboards are configured statically.
Dashboards:

- Spring Boot 2.1 Statistics [#10280](https://grafana.com/grafana/dashboards/10280)


### configure eureka
Prometheus works only with consul service diskovery, to add consul endpoints [#eureka-consul-adapter](https://github.com/twinformatics/eureka-consul-adapter)

### configuring spring boot apps
Turn on Prometheus support in actuator and enable endpoint with `micrometer-registry-prometheus`
