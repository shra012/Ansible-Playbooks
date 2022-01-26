# A Vagrant box kubernetes cluster.

This project aims to install a rancher k3s single node cluster inside a vagrant box. It uses ansible_local provisioning to install the k3s and grants permissions to the `vagrant` user inside the box to access the cluster through `kubectl`.
