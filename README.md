## ELK-Playbooks
Container of ELK development poject
Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.
https://github.com/JTillsondev/ELK-Playbooks/blob/main/netdiagram.jpg

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the /ansible file may be used to install only certain pieces of it, such as Filebeat.

# This document contains the following details:

Description of the Topology
Access Policies
ELK Configuration

Beats in Use
Machines Being Monitored


How to Use the Ansible Build


# Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly stable, in addition to restricting user load to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the user volume and system access.

The configuration details of each machine may be found below.
| Name     | Function      | IP       | OS    |   |
|----------|---------------|----------|-------|---|
| Jumpbox  | Gateway       | 10.0.0.4 | Linux |   |
| Web-1    | dvwa/filebeat | 10.0.0.5 | Linux |   |
| Web-2    | dvwa/filebeat | 10.0.0.6 | Linux |   |
| Web-3    | dvwa/filebeat | 10.0.0.7 | Linux |   |
| ELK-vm-1 | ELK server    | 10.1.0.5 | Linux |   |






# Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the ELK machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 
74.128.115.73

Machines within the network can only be accessed by Jumpbox.

A summary of the access policies in place can be found in the table below.

| Name     | Public Access | Allowed IP    |
|----------|---------------|---------------|
| Jumpbox  | yes           | 74.128.115.73 |
| Web-1    | no            | 10.0.0.4      |
| Web-2    | no            | 10.0.0.4      |
| Web-3    | no            | 10.0.0.4      |
| ELK-vm-1 | yes           | 74.128.115.73 |





# Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because future machines can be added to configuration playlists to simplify deployment through automation.

The playbook implements the following tasks:

TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.

*Install docker

*Install python

*Increase and utilize more virtual memory

*Download and launch ELK container

The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.
https://github.com/JTillsondev/ELK-Playbooks/blob/main/elkscreenshot.PNG

# Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.5
10.0.0.6
10.0.0.7

We have installed the following Beats on these machines:
Filebeats

These Beats allow us to collect the following information from each machine:
Filebeats collects and forwards log files from local files.


# Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:

Copy the filebeat-playbook.yml file to /etc/filebeat/filebeat.yml.
Update the ansible host list file to include destination IPs
Run the playbook, and navigate to the destination <ELK ip address>:5601/app/kibana to check that the installation worked as expected.
