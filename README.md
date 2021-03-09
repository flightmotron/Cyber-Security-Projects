## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Project 1: ELK Stack] (Images/ELK Stack Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - install-elk.yml 

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _The off-loading function of the load balancer defends against distributed denial-of-service (DDoS) attacks. The JumBox prevents unwanted exposer of the network to the public_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _Filebeat monitors the Apache server and MySQL database logs generated by DVWA_
- _Metricbeat collects specified metrics and statistics in the resource group_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name         | Function    | IP Address                | Operating System |
|--------------|-------------|---------------------------|------------------|
| Jump Box     | Gateway     | 10.0.0.09 / 52.175.226.211| Linux            |
| Web 1        | Configure   | 10.0.0.10                 | Linux            |
| Web 2        | Load Balance| 10.0.0.11                 | Linux            |
| Web 3        | Load Balance| 10.0.0.12                 | Linux            |
|ElkServerHost | Mon. / Log. | 10.1.0.4 / 52.251.56.102  | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _205.197.212.210_

Machines within the network can only be accessed by ssh.
- _10.0.0.09_

A summary of the access policies in place can be found in the table below.

| Name         | Publicly Accessible | Allowed IP Addresses      |
|--------------|---------------------|---------------------------|
| Jump Box     | Yes                 |  205.197.212.210          |
| Web 1        | No                  |  10.0.0.09                |
| Web 2        | No                  |  10.0.0.09                |
| Web 3        | No                  |  10.0.0.09                |
|ElkServerHost | Yes                 |  10.0.0.9 /205.197.212.210| 

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _being an open source automation platform, it increases productivity and standardizes deployments_

The playbook implements the following tasks:
- _Make sure docker is installed_
- _Pull Elk Image from the elk regisitry via a shell prompt_ 
- _Run the container that starts the ELK stack_

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![ELK Docker PS Screencap](Images/ELK Docker PS.jpg)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _10.0.0.09 | 10.0.0.10 | 10.0.0.11 | 10.0.0.12_ 

We have installed the following Beats on these machines:
- _Filebeat; Metricbeat_

These Beats allow us to collect the following information from each machine:
- __Filebeat monitors the Apache server and MySQL database logs generated by DVWA_
- _Metricbeat collects specified metrics and statistics in the resource group like servers "uptime"_

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _install-elk.yml | ElkServerHost VM
- _hosts.yml | Groups: When you run playbooks with Ansible, you specify which group to run them on. This allows you to run certain playbooks on some machines, but not on others. _
- _http://52.251.56.102:5601/app/kiban

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._ 
