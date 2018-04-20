# Wordpress on Kubernetes

This project is to validate the example provided in kubernetes examples to deploy a stateful application

https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/


## Setup

### Verifgy that kubectl is installed

```kubectl version```

### Create a Secret for MySQL Password

```kubectl create secret generic mysql-pass --from-literal=password=YOUR_PASSWORD```

### Deploy MySQL

```kubectl create -f mysql-deployment.yaml```

### Deploy WordPress

```kubectl create -f wordpress-deployment.yaml```

### Verify status of all nodes using

```kubectl get all```

## Cleaning up

### Delete your Secret

```kubectl delete secret mysql-pass```

### Delete all Deployments and Services

```
kubectl delete deployment -l app=wordpress
kubectl delete service -l app=wordpress
```

### Delete the PersistentVolumeClaims

```kubectl delete pvc -l app=wordpress```
