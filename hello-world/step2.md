##Install Knative

Install Istio
`kubectl apply --filename https://raw.githubusercontent.com/knative/serving/v0.1.1/third_party/istio-0.8.0/istio.yaml`{{execute}}

Label the default namespace with istio-injection=enabled:
`kubectl label namespace default istio-injection=enabled`{{execute}}


Monitor the Istio components until all of the components show a STATUS of Running or Completed: 
`watch -n 1 kubectl get pods --namespace istio-system`{{execute}}

Run the kubectl apply command to install Knative and its dependencies
`kubectl apply --filename https://github.com/knative/serving/releases/download/v0.1.1/release.yaml`{{execute}}


Monitor the Knative components until all of the components show a STATUS of Running:
`watch -n 1 kubectl get pods --namespace knative-serving`{{execute}}
`watch -n 1 kubectl get pods --namespace knative-build`{{execute}}
