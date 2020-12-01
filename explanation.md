### Ansible Instrumentation Steps
- Create a directory for the project mkdir ansible-IP
- cd ansible-IP
- Create a custom Vagrantfile using the geerlingguy/ubuntu2004 image
#### Disable SSH host keys checking
- Create a hosts file with the IP addresses of the client, backend and database virtual machines 
- Display SSH configs using the command vagrant ssh-config and note the port, IdentityFile and user
- Create ansible.cfg file 
  - Provide the security settings using the information from the vagrant ssh-config command. 
  - Disable host key checking by typing host_key_checking = False in the file

#### Provision the servers 
- Create the playbook.yaml file that ansible will use to provision the servers listed in the hosts file. 
- Edit the Vagrantfile to use Ansible to provision the servers by adding the below just before the end
  ###### Ansible provisioning.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yaml"
  end

#### Create the virtual servers
- Run the following vagrant commands in the terminal:
  - vagrant up
  - vagrant provision < vm-instance-name > (incase it does not automatically start the playbook)
  - vagrant status - confirm that all virtual machines are running

#### Browse the app
Open the browser and visit the following address http://192.168.60.4:3000
Add a new product by clicking the add products button and then refresh the browser to view the recently added product displayed. 

### Troubleshooting
Incase you are not able to add a new product. SSH to the backend virtual machine and check the firewall status using the commands below:
* vagrant ssh backend     - SSH to the backend
* sudo ufw status         - Check if firewall is active
* sudo ufw enable         - Enable the firewall to run at boot
* sudo ufw allow ssh      - Allow SSH
* sudo ufw allow 2222/tcp - Allow port 2222
* sudo ufw allow 5000/tcp - Allow port 5000
* sudo reboot             - Reboot the virtual machine

