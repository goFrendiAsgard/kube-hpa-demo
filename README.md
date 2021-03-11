# What is it?

HPA Demo with kubernetes. Source: https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale-walkthrough/

# Prerequisites

* Kubernetes
* kubectl

# How to run

```sh
kubectl apply -f deployment.yaml -f hpa.yaml -f service.yaml
```

# How to test the HPA

```sh
kubectl run -i --tty load-generator --rm --image=busybox --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- http://php-apache; done"
```

# How to clean up

```sh
kubectl delete service php-apache
kubectl delete deployment php-apache
kubectl delete horizontalpodautoscaler php-apache
```