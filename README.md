# ansible-docker-elasticsearch
Run elasticsearch cluster on docker containers (without orchestration)

Ansible playbook to run simple [Elasticsearch with Docker](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html) with:

* [Prometheus](https://prometheus.io/) monitoring with [node_exporter](https://github.com/prometheus/node_exporter/) and [elasticsearch_exporter](https://github.com/justwatchcom/elasticsearch_exporter/)

* [Alertmanager](https://github.com/prometheus/alertmanager) to send alert to Slack

* [Grafana](https://github.com/grafana/grafana-docker) to check metrics

* [Cerebro](https://github.com/dylanmei/docker-cerebro) for administering elasticsearch cluster

## Grafana
A couple of dashboards you can find in
[dashboards](dashboards/)


## Alertmanager
set slack parameters (web hook address and channel) in

```sh
vars/monitoring_vars.yml
```

## Test it!
Install VirtualBox, Vagrant, git clone and ...

```sh
$ vagrant up
```

This command will create 5 nodes runing CentOS7

Node config: 2 CPU / 1.5 Gb RAM / 40 Gb disk

1st node - monitoring and manage tools

All the rest nodes will hold elasticsearch containers
