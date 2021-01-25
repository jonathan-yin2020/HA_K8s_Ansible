# Kubernetes Cluster on Snowball using Ansible
* Create eight Centos7 instances. In this setup includes two proxy, three masters , and three workers.
* Copy the SSH key that will be use to access all instances to /home/centos/.ssh/tmp.pem
* Change the key permission to 400
* Download and install Ansible on the Controller instance.

```
sudo yum install -y epel-release
sudo yum install -y ansible
```

* Clone this repository to your Controller instance.
* Modify ansible.cfg to match your ssh key location(if you put your key in different path other than default).
* Modify you hosts and env_variables file to match your enviorment(to match your own IPs and Hostnames).

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

