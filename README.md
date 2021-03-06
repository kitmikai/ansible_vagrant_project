# Ansible Vagrant Configuration Management Project

### Ansible Instrumentation Requirements
- Set a development environment by provisioning a Vagrant virtual machine with the latest Ubuntu server (Jeff Geerlings ubuntu 20.04). No authentication keys or certificates are needed for this project.
- Implement the following concepts in the ansible playbook:
  - Variables
  - Roles and
  - Blocks and tags

  This is a multi-server deployment and will create 3 virtual machines. Further instructions about how you can start from scratch can be found in the explalation.md file.

### Requirements
This project assumes a Linux operating system. To successfully run this project, the following software needs to be installed in your computer:
- [**Ansible**](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-ubuntu)
- [**VirtualBox**](https://www.virtualbox.org/wiki/Linux_Downloads)
- [**Vagrant**](https://linuxize.com/post/how-to-install-vagrant-on-ubuntu-18-04/)
### Installation 
* Clone this [**repository**](https://github.com/kitmikai/ansible_vagrant_project.git)
* If you are running on a computer with less than 8GB of RAM please edit the line with v.memory = 1024, and change to v.memory = 512
* cd ansible_vagrant_project 
* Run the command vagrant up
* Run the command vagrant status to confirm that the virtual machines are running
* When Ansible has completed running, visit http://192.168.60.4:3000 and click add a product. Refresh the browser to view the recently added product. 

### Stopping the virtual machines
To stop the virtual machines, run the command:
* vagrant halt