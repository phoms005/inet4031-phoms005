# Week 6: GitHub Actions and Prometheus

Prometheus is installed in the monitoring namespace using the Prometheus Community Helm chart.

Configuration overrides are in `prometheus-values.yaml`.

Keep this port-forward running to query Prometheus:

```bash
kubectl port-forward -n monitoring service/prometheus-server 9090:80
```

Run queries from the repository root:

```bash
./week-6/pq.sh 'up'
./week-6/pq.sh 'sum by (deployment) (kube_deployment_status_replicas{namespace="default"})'
```
