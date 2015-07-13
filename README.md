# magnolia-ansible
An example of a deployment script for Magnolia using Ansible and Docker. 

The implementation is based on this article: http://nicolasbarbe.com/magnolia-devops-automate-deployment

## Features
- Deploy a cluster of Magnolia public instances on a given host.
- Deploy a Magnolia author instance on a given host.
- Deploy a load-balancer redirecting the traffic to the Magnolia public instances.
- Automatically register the public instances to the load-balander and the author instance as a subscriber.
- Each Magnolia instance uses its own MySQL database deployed automatically on the host.
- List all the applications installed on all hosts.
- Remove the applications and clean-up all hosts.

## Usage
The script can be run locally using the Vagrant provisioning:

```
vagrant up
ansible-playbook -i inventories/local site.yml
```

The script can be run on production providing a new inventory file:

```
ansible-playbook -i inventories/production site.yml
```