This Deployment requires the following additional environment variables:

VSPHERE_DISK_GIB_MD_0: "50"
VSPHERE_MEM_MIB_MD_0: "2048"
VSPHERE_NUM_CPUS_MD_0: "4"
VSPHERE_DISK_GIB_MD_1: "60"
VSPHERE_MEM_MIB_MD_1: "8192"
VSPHERE_NUM_CPUS_MD_1: "8"
WORKER_MACHINE_COUNT_MD_0: "2"
WORKER_MACHINE_COUNT_MD_1: "1"


These environment variable can be set either as environment variables in your system or added to the file: ~/.tkg/config.yaml

to create a cluster named multi-md-cls-01 using this yaml you can run a command like this:
tkg create cluster multi-md-cls-01 --plan=multi-md

the yaml file must be placed in the following location:
~/.tkg/providers/infrastructure-vsphere/v0.6.3/cluster-template-multi-md.yaml