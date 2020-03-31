# Solution
1. First create the Resource group.

```
az group create --name cav-uni-test --location eastus
```
You should get a response something like this.

```$xslt
{
  "id": "/subscriptions/<guid>/resourceGroups/cav-uni-test",
  "location": "eastus",
  "managedBy": null,
  "name": "cav-uni-test",
  "properties": {
    "provisioningState": "Succeeded"
  },
  "tags": null
}
```

2. Create a new cluster using the following command

```$xslt
az aks create --resource-group cav-uni-test --name myAKSCluster --node-count 1 --generate-ssh-keys
```

3. Log into your newly created cluster.
```$xslt
az aks get-credentials --resource-group cav-uni-test --name myAKSCluster
```

4. Verify the connection by running.
```$xslt
kubectl get nodes
```

You can read about creating a cluster in the portal [Here](https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough-portal)