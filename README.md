The playbooks and roles are previews to the F5 modules included in Ansible 2.4

To use:

1) Edit the f5-secrets.yml in this directory and supply the necessary credentials.

2) Edit f5-vars.yml appropriately. The values and their intent are listed below.

tenant: The name of the customer or company<br>
data_zone: Allows the VLAN to be easily recognized as being in a DMZ, internal, or for a particular group such as accounting<br>
projectname: What the VIP front ends<br>
app_environment: dev, test, prod, et cetera<br>
pool_protocol: http, ldap, sip, et cetera<br>
pool_port: The port number assigned to the pool<br>
virt_dns_name: The DNS name of the virtual server, used as a component of the overall VIP name<br>
virt_port: The port the VIP listens on<br>
virt_ipv4_address: The IP address assigned to the VIP<br>
virt_persistence_profile: The VIP persistence profile<br>

The python list "nodes" contains all the names and addresses of the nodes that will be placed in the pool.

The python list "bigip_cluster_members" contains the management addresses of the cluster members. It can contain more than two values. Ansible uses these addresses for configuration.

The python list "bigip_self_ips" controls what self IPs are assigned to the cluster members. There must be one self IP for each, and they are assigned in respective order, e.g. the first cluster member gets the first self IP.


3) Run the playbooks.

ansible-playbook bigip-newtenant.yml<br>
ansible-playbook bigip-newvip.yml
