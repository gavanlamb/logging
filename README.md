# Logging

# Config
## Update default logging driver
1. Install loki plugin: ` docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions`
2. Update Docker daemin config on all nodes   
    `/etc/docker/daemon.json`
    ```json
    {
        ...
        "log-driver": "loki",
        "log-opts": {
            "loki-url": "http://192.168.50.32:3200/loki/api/v1/push",
            "loki-batch-size": "100",
            "loki-retries": "5"
        }
    }
    ```

# TODO
## LATER
### Ship trace id with logs for all services above
### - Update grafana datasource for tempo to support queries

### Add labels to logs
### - Instance Id
### - Trace Id
### - Span Id

https://grafana.com/blog/2022/08/18/new-in-grafana-9.1-trace-to-metrics-allows-users-to-navigate-from-a-trace-span-to-a-selected-data-source/
https://grafana.com/blog/2022/05/09/new-in-grafana-8.5-how-to-jump-from-traces-to-splunk-logs/?pg=blog&plcmt=body-txt
https://grafana.com/docs/grafana/latest/fundamentals/exemplars/
https://grafana.com/blog/2021/09/23/intro-to-distributed-tracing-with-tempo-opentelemetry-and-grafana-cloud/?pg=blog&plcmt=body-txt
https://grafana.com/docs/grafana/latest/fundamentals/exemplars/
https://grafana.com/docs/grafana/latest/setup-grafana/configure-grafana/feature-toggles/
https://grafana.com/docs/grafana/latest/setup-grafana/configure-grafana/#feature_toggles
