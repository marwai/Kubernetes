# logging
### Commands to get started

- stdout 
- kubectl logs

Once application is running in staging or production, consider 
using a loggin platform like Kibana or ElasticSearch, with logs being shiiped to them from pods using Fluentd
or Filebeat (Logstash) 


### Monitoring
- Node health
- K8 cluster
- Application health (and metrics)

### cAdvisor
- Open-source usage collector that was built for containers 
- Aut-discovers all containers in the given node and collect CPU, memory, filesystem and network usage statistics
- Provide overal machine usage by analysing root container on machine

### Prometheus
- Open-source systems monitoring and alerting toolkit
- application metrics and monitor k8 via projects like kube-prometheus

#
