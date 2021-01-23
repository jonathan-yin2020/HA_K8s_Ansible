# Kubernetes Cluster on Snowball using Ansible
* Download and install Ansible on the Controller instance.

```
sudo yum install epel-release
sudo yum install ansible
```

* Clone this repository to your Controller instance.
* Modify ansible.cfg to match your ssh key location.
* Modify you hosts and env_variables file to match your enviorment.
* Create seven Centos7 instances. In this setup includes one proxy, three masters , and three workers.

* Run the following command to setup the HA K8s cluster.

```
ansible-playbook Create_HA_k8s.yml
```

* Once completed, you can check the K8s Cluster status by running the following command on your controller instance.

```
kubectl get node -o wide
kubectl get pod -n kube-system
```

## Additional information

