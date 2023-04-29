# Geth helm chart
Basic Helm chart to deploy a Geth node in a Kubernetes environment. 

## Install 
`helm install <release-name> .`

## Customize
- Eth mainnet is targeted as default network. You can easily add the `--goerli` or `--sepolia` flags in the `node-statefulset.yaml` file to sync a node for test networks.
- The default storageclass value `standard`  is used in  `values.yaml` , which means Geth will sync over an HDD. To get a faster syncing time you can use the `ssd-storageclass.yaml` file, apply it with: `kubectl apply -f ssd-storageclass.yaml` and change the `standard` value to `faster`. This way Geth will sync over SSD
- Current `ssd-storageclass.yaml` file is targeted for GKE. See [this](https://docs.aws.amazon.com/eks/latest/userguide/storage-classes.html) if using AWS
 or [this](https://docs.microsoft.com/nl-nl/azure/aks/concepts-storage) if using Azure 

