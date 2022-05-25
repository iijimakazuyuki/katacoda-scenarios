Kubernetes will start in the environment.

Execute following command to wait for Kubernetes starting:

`launch.sh`{{execute}}

If any CoreDNS pods is running on the controlplane in the environment, pods on a worker node may not be able to resolve domain names.

Execute following command to patch the CoreDNS deployment so that CoreDNS will not run on the controlplane:

`kubectl -n kube-system patch deploy coredns --type json -p '[{"op":"remove","path":"/spec/template/spec/tolerations/1"}]'`{{execute}}
