# ansible-docker-elasticsearch
Run elasticsearch cluster on docker containers

Ansible playbook to [Install Elasticsearch with Docker](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html)

[Prometheus](https://prometheus.io/) monitoring with [node_exporter](https://github.com/prometheus/node_exporter/) and [elasticsearch_exporter](https://github.com/justwatchcom/elasticsearch_exporter/)

[Alertmanager](https://github.com/prometheus/alertmanager) to send alert to Slack

[Grafana](https://github.com/grafana/grafana-docker) to check metrics 

[Cerebro](https://github.com/dylanmei/docker-cerebro) for administering elasticsearch cluster

## Test it!
Install VirtualBox, Vagrant, git clone and ... 

```sh
$ vagrant up
```

