

# Configuration

## Files

The yaml file must be placed in the following location:
~/.tkg/providers/infrastructure-vsphere/v0.6.3/cluster-template-multi-md.yaml

## Required Additional Environment Variables:

VSPHERE_DISK_GIB_MD_0: "50"

VSPHERE_MEM_MIB_MD_0: "2048"

VSPHERE_NUM_CPUS_MD_0: "4"

VSPHERE_DISK_GIB_MD_1: "60"

VSPHERE_MEM_MIB_MD_1: "8192"

VSPHERE_NUM_CPUS_MD_1: "8"

WORKER_MACHINE_COUNT_MD_0: "2"

WORKER_MACHINE_COUNT_MD_1: "1"


# INSTRUCTIONS
These environment variable can be set either as environment variables in your system or added to the file: ~/.tkg/config.yaml

## Creating a cluster
to create a cluster named multi-md-cls-01 using this yaml you can run a command like this:
tkg create cluster multi-md-cls-01 --plan=multi-md

## Scaling the worker nodes count for a specific machine deployment
currently there is no way to scale the machine deployments via tkg cli as we have edited the config. in order to scale we will edit the clusterapi deployed crd of the machine deployment via the management cluster.

1. connect to the context of the management cluster via kubectl.
     kubectl config use-context <MGMT CLUSTER CONTEXT NAME>
2. list the machine deployment objects via the following command
     kubectl get machinedeployments.cluster.x-k8s.io -A
3. now that we have found the machine deployment we want to scale
