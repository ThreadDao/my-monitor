# my-monitor
To monitor chaos cluster node disk stats

## Manage prometheus.yml by ConfigMaps

```angular2html
kubectl create -f prometheus-config.yml
```

## Authorize access to Prometheus

1. Define a role (ClusterRole) and give the corresponding access permissions
2. Create the account (ServiceAccount) used by Prometheus
3. Bind the account to the role (ClusterRoleBinding)

```angular2html
kubectl create -f prometheus-rbac-setup.yml
```

## Deploy a Prometheus Server instance through Deployment

```angular2html
kubectl create -f prometheus-deployment.yml
```

## Deploy node-exporter in Each Node by DaemonSet

```angular2html
kubectl create -f node-exporter-daemonset.yml
```

## Deploy Grafana
```angular2html
sudo docker run -d -p 3000:3000 grafana/grafana
```

Reference:

[1] https://yunlzheng.gitbook.io/prometheus-book/part-iii-prometheus-shi-zhan/readmd/use-prometheus-monitor-kubernetes#shi-yong-nodeexporter-jian-kong-ji-qun-zi-yuan-shi-yong-qing-kuang

[2] https://grafana.com/docs/grafana/latest/installation/kubernetes/

[3] https://www.prometheus.wang/quickstart/use-grafana-create-dashboard.html
