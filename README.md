# Automated Service Deployment and Management in OpenStack

This project is an automated solution for deploying, operating, and managing scalable and resilient cloud-based service infrastructure within an OpenStack environment.

Key Features
1. Automated Deployment: Utilizes Ansible playbook and bash/shell scripts to set up a cloud environment in OpenStack automatically, including creating networks, routers, subnets, security groups, servers/nodes.
2. High Availability and Load Balancing: Implements load balancing with HAProxy and high availability with Keepalived across dual proxy nodes to eliminate a single point of failure.
3. Secure Access: Configures a BASTION host for secure SSH access to instances and centralized monitoring using Prometheus and Grafana.
4. Resource Cleanup: Includes script to clean up and release all resources allocated during the deployment phase, ensuring no residual resources are left behind.

Project Components
'install' Script: Automates the deployment of the entire environment, including network setup, instance creation, and service configuration.
'operate' Script: Manages the ongoing operations, including dynamic scaling and monitoring of service nodes.
'cleanup' Script: Removes all resources and cleans up the environment after use.
Monitoring Configuration: Integrates Prometheus and Grafana for monitoring the deployed services and infrastructure.
Load Balancing Configuration: Configures HAProxy and Keepalived for load balancing.

Working  
1. Deployment: Run the 'install' script with OpenStack credentials(open-rc file), which sets up the environment and deploys the necessary services.
2. Operation: The 'operate' script monitors the system, and adjusts the number of service nodes as mentioned in the 'server.conf' file.
3. Cleanup: The 'cleanup' script releases all resources, returning the cloud environment to its original state.

Usage Instructions
1. Provide permissions to install, operate, and cleanup script files.
```bash
chmod +x install operate cleanup
```
2. Generate ssh keys, the ssh keys are to be present in the ssh directory and permissions to the key
```bash
ssh-keygen -t rsa 
chmod 600 <path to the key pair>
```
3. open-rc file to be present in the working directory
```bash
source <name of open-rc file>
```
4. To run install script
```bash
./install <name of open-rc file> <tag> <path to generated public key>
```
5. To run operate script
```bash
./operate <name of open-rc file> <tag> <path to generated public key>
```
6. To run cleanup script
```bash
./cleanup <name of open-rc file> <tag> <path to generated public key>
```
 






