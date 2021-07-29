## Description
The goal of this lab is to know how to install on Kubernetes and get started
## Litmus Installtion
Helm must be first installed, to check that you can try ```sh  helm -v```
##### Add the LitmusChaos Helm repo
```sh  
helm repo add litmuschaos https://litmuschaos.github.io/litmus-helm/
```
##### Create a Litmus namespace in Kubernetes
```sh  
kubectl create ns litmus
```
##### install the Litmus Helm chart
```sh  
helm install chaos litmuschaos/litmus --namespace=litmus  
```

afterwards check and wait for ChaosOperator to be installed and up and running
```sh
kubectl get pods -n litmus  -w
```
