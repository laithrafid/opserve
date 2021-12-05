#Opserve includes opensource observation-stack for testing

 ## Docker hosts and containers 
Based on the official Docker images from Elastic:

* [Prometheus](https://prometheus.io/),
* [Grafana](http://grafana.org/), 
* [cAdvisor](https://github.com/google/cadvisor),
* [NodeExporter](https://github.com/prometheus/node_exporter) and alerting with 
* [AlertManager](https://github.com/prometheus/alertmanager).
* [Elasticsearch](https://github.com/elastic/elasticsearch/tree/master/distribution/docker)
* [Logstash](https://github.com/elastic/logstash/tree/master/docker)
* [Kibana](https://github.com/elastic/kibana/tree/master/src/dev/build/tasks/os_packages/docker_generator)
* [capanalysis](https://hub.docker.com/r/laithrafid/capanlysis)

Other available stack variants:

* [`tls`](https://github.com/deviantony/docker-elk/tree/tls): TLS encryption enabled in Elasticsearch.
* [`searchguard`](https://github.com/deviantony/docker-elk/tree/searchguard): Search Guard support

