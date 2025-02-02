# IBM Cloud Kubernetes Service

You'll first need to get started with IBM Cloud Kubernetes Service by setting up
an IBM Cloud account. For details, see the
[getting started](https://cloud.ibm.com/docs/containers?topic=containers-getting-started)
instructions. Then follow the steps below to create a cluster and run the
conformance tests.

## Create a cluster

If you haven't already done so,
[install the CLI](https://cloud.ibm.com/docs/containers?topic=containers-cs_cli_install#cs_cli_install_steps)
for IBM Cloud Kubernetes Service. You may then create a cluster using the CLI
or UI.

### CLI

```
$ ibmcloud ks cluster-create --name conformance --kube-version 1.15 --zone <zone name> --machine-type <machine type> [--workers <number of workers>] [--private-vlan <private VLAN> --public-vlan <public VLAN>]
```

### UI

Go to [IBM Cloud catalog](https://cloud.ibm.com/catalog?category=containers)
and select `Kubernetes Cluster` and follow the instructions to create a cluster.

## Run conformance tests

Wait for the cluster and all worker nodes to reach `normal` state.

```
$ ibmcloud ks cluster-config --admin conformance
$ ibmcloud ks cluster-get conformance
$ ibmcloud ks workers conformance
```

Then follow the
[test instructions](https://github.com/cncf/k8s-conformance/blob/master/instructions.md#running)
to run the conformance tests.
