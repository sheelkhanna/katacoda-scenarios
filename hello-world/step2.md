##Install Knative

Install Istio

`kubectl apply --filename https://raw.githubusercontent.com/knative/serving/v0.1.1/third_party/istio-0.8.0/istio.yaml`{{execute}}

Label the default namespace with istio-injection=enabled:

`kubectl label namespace default istio-injection=enabled`{{execute}}


Monitor the Istio components until all of the components show a STATUS of Running or Completed: 

`watch -n 1 kubectl get pods --namespace istio-system`{{execute}}

Run the kubectl apply command to install Knative and its dependencies

`kubectl apply --filename https://github.com/knative/serving/releases/download/v0.1.1/release-lite.yaml`{{execute}}


Monitor the Knative components until all of the components show a STATUS of Running:

`watch -n 1 kubectl get pods --all-namespaces`{{execute}}

Find the IP address of service

`kubectl get svc knative-ingressgateway --namespace istio-system`{{execute}}


Find URL of the service
`kubectl get services.serving.knative.dev helloworld-go  --output=custom-columns=NAME:.metadata.name,DOMAIN:.status.domain`{{execute}}
