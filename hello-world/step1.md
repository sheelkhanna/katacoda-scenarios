Setup the Kubernetes Dashboard


Start kubernetes by running launch.sh

`launch.sh`{{execute}}

Verify k8s is running

`kubectl cluster-info`{{execute}}

Install Dashboard 

`kubectl create -f \
https://raw.githubusercontent.com/kubernetes/dashboard/master/src/deploy/recommended/kubernetes-dashboard.yaml`{{execute}}

Verify Dashboard pod is running

`kubectl get po --all-namespaces`{{execute}}

Expose dashboard on port 8443

`kubectl -n kube-system port-forward \
$(kubectl -n kube-system get po -l k8s-app=kubernetes-dashboard -oname | cut -d/ -f 2) 8443:8443`{{execute}}

