# project13-2020
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Network Diagram](https://github.com/sumiya23/project13-2020/blob/main/Diagrams/Untitled%20Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yml file may be used to install only certain pieces of it, such as Filebeat.

  [install Elk.yml ]( https://github.com/sumiya23/project13-2020/blob/main/Ansible/13-Elk-Stack-Project_Activities_Stu_Day_1_Solved_Resources_install-elk.yml)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be reliable, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect?  Load balancer protect availability. What is the advantage of a jump box? it creates a single point of entry reducing risk of exposure.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system logs
- _TODO: What does Filebeat watch for? changes to protected files.
- _TODO: What does Metricbeat record? changes to system utilization.

The configuration details of each machine may be found below.


| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1    |Container | 10.0.0.5   | Linux            |
| Web-2    |Container | 10.0.0.6   | Linux            |
/Network/Network interfaces.png 


 
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_47.12.31.182

Machines within the network can only be accessed by jumpbox
- _TODO: Which machine did you allow to access your ELK VM?  Only the jumpbox What was its IP address?_ 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 47.12.31.182         |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? allowed to configure multiple VMs at the sametime.

The playbook implements the following tasks:
- install docker
- configure settings
- download a container 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Sudo Docker PS](https://github.com/sumiya23/project13-2020/blob/main/Images/pic%20of%20docker%20.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.6 and 10.0.0.7

We have installed the following Beats on these machines:
- filebeat and metricbeat

These Beats allow us to collect the following information from each machine:
- filebeat allows monitoring of protected file changes
- metricbeat allows monitoring of system resource usage

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the config file to vm 
- Update the hosts file to include private ip address
- Run the playbook, and navigate to target vm to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it? yml file and you copy it to the play-book directory.
- _Which file do you update to make Ansible run the playbook on a specific machine?  you update to hosts file. How do I specify which machine to install the ELK server on versus which to install Filebeat on? you specify the server ips.
- _Which URL do you navigate to in order to check that the ELK server is running? the Elk server public ip.

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc. ansible-playbook.yml.

