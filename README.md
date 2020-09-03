## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Week 12 Homework.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

![filebeat config](Project_files/filebeatconfig.yml)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly responsive, in addition to restricting traffic to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log and system files.
- _TODO: What does Filebeat watch for?_ Watches for changes in files used or generated 
- _TODO: What does Metricbeat record?_ Collects statistics from services running on the server

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.5   | Linux            |
| Web 1    | DVWA     | 10.0.0.6   | Linux            |
| Web 2    | DVWA     | 10.0.0.7   | Linux            |
| ELK      |Monitoring| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 24.10.195.121
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by Jumpbox.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_HOME 24.10.195.121

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | yes                 | 24.10.195.121        |
| ELK      | yes                 | 24.10.195.121        |
| Web1     | no                  | 52.183.58.61         |
| Web2     | no                  | 52.183.58.61         |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_Easy configuration of connected VM�s

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install docker
- Install python3
- Install docker with python module
- Use sysctl module
- Download and launch docker web container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: 52.183.58.61, 10.0.0.6, 10.0.0.7 

We have installed the following Beats on these machines:
- _TODO: Filebeat, Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
! Filebeat monitors the log files or locations that you specify, collects log events, and forwards them to Elasticsearch
Metricbeat helps you monitor your servers by collecting metrics from the system and services running on the server

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the yaml file to host VM.
- Update the yaml file to include...
- Run the playbook, and navigate to to host VM to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- Which file is the playbook? The yaml(.yml) file is the playbook.
Which file do you update to make Ansible run the playbook on a specific machine? 
- You must update the hosts file.
How do I specify which machine to install the ELK server on versus which to install Filebeat on? 
- In the heading of the yaml file next to host, specifify which machine you want to perform the install using the category you listed the machine on in the hosts file.
Which URL do you navigate to in order to check that the ELK server is running? 
- 52.165.30.82/kibana/app
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
