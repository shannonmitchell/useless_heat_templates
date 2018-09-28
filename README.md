# Useless Heat Templates
Dumping ground for some temporary junk heat templates.

## linuxacademy-cka-setup.yml 

Example:
```bash
openstack --os-cloud phobos stack create -t linuxacademy-cka-setup.yml --parameter step=init_n_slaves shannon-kubernetes
```

Parameters:

* image: 'CentOS 7' or 'Ubuntu 16.04' with ubuntu being the default.
* slave_nodes: Slave node count with a default of 3.
* slave_flavor: Flavor to use for the slave nodes.
* master_flavor: Flavor to use for the master node.
* key_name: You existing ssh key name in openstack to be used for connecting to the vms.
* network_id: Openstack neutron network id to connect your vms to.
* step: 'noaction, 'reposetup' or 'init_n_slaves' with a default of noaction.  
  * 'noaction': If you want to do kube cluster from scratch use noaction.  
  * 'reposetup': If you want to have the repos set up with docker.io, kubeadm, kubelet and kubectl installed only.
  * 'init_n_slaves': If you want to have the reposetup actions taken as well as the cluster set up with flannel and slaves joined.

