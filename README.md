# Project Title

A provisioning project to build a virtual machine in On-Premise environment using Vagrant (Hashicorp) tool, and afterward mount an ElasticSearch / Fluentd / Kibana solution over there applying Ansible Playbook roles. The model does not include any kind of configuration of index patterns: the main goal is to provide a general concept of Devops Provisioning

## Getting Started

Create a private key into the local folder, after cloning this repository using git.

### Prerequisites

You must first install the following applications to achieve the goals:

Vagrant Hashicorp
Ansible 
Oracle VM Box 

In case you are using a Linux Subsystem for Windows, enable the WSL settings and the path for the VM Box in the bashrc file 

### Installing

##### 0. Before getting started, we must initialize Vagrant
vagrant init

#### 1. Mount the virtual machine using Vagrant 
vagrant up 

#### 2. Get access to the new virtual machine and save your password
ssh vagrant@127.0.0.1 -p 2222 

#### 3. Generate your key and copy it into the new virtual machine
ssh-copy-id -i ~/.ssh/id_rsa.pub vagrant@127.0.0.1 -p2222 

#### 3. Execute the ansible playbook 
ansible-playbook -i inventory deploy.yml

### Running the tests
#### Open the navigator or browser in your machine and try to see the Kibana dashboard installed over the virtual machine 

http://192.168.56.103/app/kibana#/home?_g=()

## Authors

* **Jorge Andres Robiola** 

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Mariano Buglione
* Julian Heredia
* David Sanchez


