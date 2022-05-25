Kubernetes will start in the environment.

Execute following command to wait for Kubernetes starting:

`launch.sh`{{execute}}

If two CoreDNS pods is running in the environment, pods may not be able to resolve domain names.

Execute following command to scale the CoreDNS pods to 1:

`kubectl scale deploy -n kube-system coredns --replicas=1`{{execute}}
