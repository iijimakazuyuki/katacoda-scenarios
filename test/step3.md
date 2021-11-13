`manifest-application.yaml`{{open}}

`kubectl apply -f manifest-application.yaml`{{execute}}

`kubectl port-forward svc/podinfo 80:9898 --address 0.0.0.0 > /dev/null`{{execute}}
