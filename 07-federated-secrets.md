# Federated Secrets

Kubernetes supports the federation of secrets across multiple clusters. Federated secrets are automatically created on new clusters added to the federation.

## Prerequisites

```
kubectl config use-context federation-cluster
```

## Federate Secrets

The following command will create the `federated` secret across all 4 clusters:

```
kubectl create secret generic federated --from-literal=password=foo
```

```
secret "federated" created
```

### Verify

List the `federated` secret

```
bash -x list-secrets
```
