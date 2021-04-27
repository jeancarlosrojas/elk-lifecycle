# Implementing a Hot-Warm-Cold Architecture with Index Lifecycle Management

Requirements:
* Kubernetes o Minikube
* Helm v3

```sh
#Deploy 1 node of elasticsearch-master 
$ helm install elasticsearch-master elastic/elasticsearch --version 7.12.0 -f elasticsearch-master/values_master.yaml --namespace elastic

#Deploy 2 nodes elasticsearch-hot-master
$ helm install elasticsearch-hot-master elastic/elasticsearch --version 7.12.0 -f elasticsearch-master/values_hot_master.yaml --namespace elastic

#Deploy 1 nodes elasticsearch-warm-master
$ helm install elasticsearch-warm-master elastic/elasticsearch --version 7.12.0 -f elasticsearch-master/values_warm_master.yaml --namespace elastic

#Deploy 1 nodes elasticsearch-cold-master
$ helm install elasticsearch-cold-master elastic/elasticsearch --version 7.12.0 -f elasticsearch-master/values_cold_master.yaml --namespace elastic

#Deploy Kibana
$ helm install kibana elastic/kibana --version 7.12.0 -f elasticsearch-kibana/values.yaml --namespace elastic

#Deploy Filebeat
$ helm install filebeat elastic/filebeat --version 7.12.0 -f elasticsearch-filebeat/values.yaml --namespace elastic
```
