## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

-	Images/Network_Diagram.pdf)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

-	etc/ancible/install-elk.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly responsive, in addition to restricting access to the network.
-	Load balancers protect the availability of a network. The advantage of a jump box is the ability to access and manage devices in separate security zones. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.
- Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash. Metricbeat helps you monitor your servers by collecting metrics from the system and services running on the server, such as: Apache. 

The configuration details of each machine may be found below.

| Name     | Function    | IP Address     | Operating System |
|----------|-------------|----------------|------------------|
| Jump Box | Gateway     | 104.41.128.175 | Linux            |
| HostVM   | Gateway     | 51.143.13.136  | Linux            |
| Web1     | Web Server  |  10.0.0.5      | Linux            |
| Web2     | Web Server  |  10.0.0.6      | Linux            |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP address:
-	180-143-23-246

Machines within the network can only be accessed by the jump box.
I allowed the jump box to access my ELK VM. The IP address is 51.143.12.136. 

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Address   |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |   180-143-23-246     |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-	Ancible is very simple to use. It’s powerful and lets you model even highly complex IT workflows. Also, flexible because you can orchestrate the entire application environment no matter where it’s deployed.

The playbook implements the following tasks:
- Install Docker.io 
- Download image
- Attach Container
- Docker service systemd enable

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Images/docker_ps_screencapture.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
 - 10.0.0.5 & 10.0.0.6 

We have installed the following Beats on these machines:
- Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat collects logfiles, which we use to monitor log events. Also, metric beat collects metrics and statistics of a server, which we use to monitor system and services running on the server. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to /etc/ansible. 
- Update the host file to include the IP addresses of the machines being used. 
- Run the playbook and navigate to “Kibana” url http://51.143.13.136:5601 to check that the installation worked as expected.

![image](https://user-images.githubusercontent.com/83295723/134451591-9d126328-2d04-415d-a1c2-08ec099ebcfb.png)

