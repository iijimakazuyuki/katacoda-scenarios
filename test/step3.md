`manifest-application.yaml`{{open}}

`kubectl apply -f manifest-application.yaml`{{execute}}

`kubectl port-forward svc/podinfo 9898:9898 --address 0.0.0.0 &> /dev/null`{{execute}}
