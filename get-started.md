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
Check if chaos CRDs are installed & the api-resources are created for the same
```sh
kubectl get crds | grep litmus
```



```sh
kubectl get api-resources | grep litmus
```













Check if the roles nd rolebinding resources are created as wanted
```sh
kubectl get clusterrole,clusterrolebinding | grep litmus
```

