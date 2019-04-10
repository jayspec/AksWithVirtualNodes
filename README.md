# AksWithVirtualNodes

A project to demonstrate how to create an AKS cluster using the new Virtual Nodes feature.

## Prerequisites

1. An Azure AD service principal must already exist. See [Service principals with Azure Kubernetes Service](https://docs.microsoft.com/en-us/azure/aks/kubernetes-service-principal)
2. A KeyVault instance must already exist.  The KeyVault should contain the service principal's secret in its own secret store.
3. A Log Analytics workspace must already exist.

## Parameters

####The parameters you will need to override are:

* *environmentName*: The name of the environment to create. Will be prepended to the name of the cluster and the VNet.  This should be something like "dev", "test", or "prod".
* *clusterName*: The name of the Kubernetes cluster to create.  Will be prepended by the environmentName.
* *logAnalyticsResourceGroup*: The name of the resouce group in which you have a Log Analytics workspace.
* *logAnalyticsName*: The name of your Log Analytics workspace.
* *servicePrincipalClientId*: The ID of the cluster infrastructure service principal.
* *servicePrincipalKeyVaultSecretName*: The name of the KeyVault secret that contains the client secret for the cluster infrastructure service principal.
* *keyVaultResourceGroup*: The name of the resource group where the KeyVault containing the service principal client secret can be found.
* *keyVaultName*: The name of the KeyVault containing the service principal client secret.

####You can also override:

* *clusterLocation*: The Azure Region the cluster will be deployed to.  Defaults to the location of the Resource Group.