Start Kubernetes


Start kubernetes by running launch.sh

`launch.sh`{{execute}}

Verify k8s is running

`kubectl cluster-info`{{execute}}


Verify all pods are running

`watch -n 1 kubectl get po --all-namespaces`{{execute}}

