# Apache Superset on Kubernetes (Local Development)

## Quick Deployment Guide

### 1. Add the Superset Helm repository
```bash
helm repo add superset https://apache.github.io/superset
helm repo update
```

### 2.Update values.yaml

### 3. Install superset
```bash
helm upgrade --install superset -f values.yaml superset/superset
```
### 4. Connect cluster to localhost
```bash
# Superset web interface
kubectl port-forward svc/superset 8088:8088

# Redis
kubectl port-forward superset-redis-master-0 6379:6379

# Postgresql
kubectl port-forward superset-postgresql-0 5432:5432
```
