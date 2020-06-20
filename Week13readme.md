## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/elkdiagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _yml__ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._ playbook ansible files/ roles 

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available and secure, in addition to restricting access or DDOS to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_ 
Load balancers provide availability and reliability. 
Advantage of a jump box is limiting attack surface. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the VMs and system files_.
- _TODO: What does Filebeat watch for?_collects logs and looks  for changes.
- _TODO: What does Metricbeat record?_ records metrics such as CPU and RAM usage. Container performance.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function   | IP Address | Operating System |   |
|----------|------------|------------|------------------|---|
| Jump Box | Gateway    | 10.0.0.1   | Linux            |   |
| DVWA 1   |            | 10.0.0.9   | Linux            |   |
| DVWA 3   | Elk server | 10.0.0.11  | Linux            |   |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _jump box and load balancer machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: 22 and 80, IP 73.110.131.97

Machines within the network can only be accessed by the jump box.
- _TODO: Which machine did you allow to access your ELK VM? DVWA-VM3 IP 10.0.0.11

+----------------+---------------------+----------------------+--+--+
| Name           | Publicly Accessible | Allowed IP Addresses |  |  |
+----------------+---------------------+----------------------+--+--+
| Jump Box       |                     | 10.0.0.5             |  |  |
+----------------+---------------------+----------------------+--+--+
| External HTTP  | yes                 | all                  |  |  |
+----------------+---------------------+----------------------+--+--+
| Port 5601      | yes                 | 73.110.131.97        |  |  |
+----------------+---------------------+----------------------+--+--+
| port 9200      | no                  | no / TCP 9200        |  |  |
+----------------+---------------------+----------------------+--+--+

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_prevent errors, efficiency, fast. 

The playbook implements the following tasks:
- _TODO: -set steps to webservers.
         - apt install docker.io
          - installs docker on the linux system
         - apt install python-pip
          - installs the ability to install pip packages
         - pip install docker 
          - installs docker in python
         - launched docker web container
         
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: VM 10.0.0.9

We have installed the following Beats on these machines:
- _TODO: Filebeat and metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: Filebeat collects log events or locations which are then forwarded to Elasticsearch or Lostash for indexing. 
Metricbeat collects metrics and statistics and ships them to the output. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ___playbook__ file to __/etc/ansible___.
- Update the __yml___ file to include hosts: webservers
- Run the playbook, and navigate to /etc/ansible/roles/filebeat.yml to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? the /etc/ansible/install-elk.yml
_Where do you copy it? to /etc/ansible
- _Which file do you update to make Ansible run the playbook on a specific machine?  the hosts file
_How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ you specify by entering the specific IP address. 
- _Which URL do you navigate to in order to check that the ELK server is running? http:myip:5601

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._