# Grafana

Customizable grafana image with plugins preinstalled.

Allows you to easily preload datasources and dashboards.

All you have to do is create a new Dockerfile using `maronato/grafana` as the base image and add your dashboards:
```Dockerfile
FROM maronato/grafana:latest

# Default datasources
ADD datasources.yml /etc/grafana/provisioning/datasources/
# Dashboard api file
ADD dashboards.yml /etc/grafana/provisioning/dashboards/
# Folder with dashboards
ADD dashboards /etc/grafana/dashboards/
```

Then, create a volume mapping to `/data` to persist grafana stuff.

You'll find an example with Prometheus integration on the `example` branch of this repo.
