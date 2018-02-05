# Adding Clusters

With the federated control plane in place we are ready to start adding clusters to our federation.

To add a cluster to the federation you will need to perform the following steps:

* Create kubeconfig for each cluster and store it in a Kubernetes secret on the host cluster
* Create a cluster resource for each cluster in the federation cluster

## Prerequisites

```
kubectl config use-context host-cluster
```

### Generate kubeconfigs and cluster objects

In this section you will generate a kubeconfig and cluster resource object for each cluster in the federation.

```
mkdir clusters
```

```
mkdir -p kubeconfigs
```

```
bash -x add-clusters
```

## Create the Cluster Secrets

In this section you will create a secret to hold the kubeconfig for each cluster. 

```
bash -x add-secrets
```
## Create the cluster resources

```
kubectl config use-context federation-cluster
```

```
kubectl create -f clusters/
```

### Verify

```
kubectl get clusters
```

```
NAME             STATUS    AGE
asia-east1-b     Ready     46s
europe-west1-b   Ready     45s
us-central1-b    Ready     44s
us-east1-b       Ready     43s
```
