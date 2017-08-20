The playbooks and roles are previews to the F5 modules included in Ansible 2.4

To use, edit the f5-secrets.yml in this directory and supply the necessary credentials.

Next, edit f5-vars.yml appropriately. The values and their intent are listed below.

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

Last, run the playbooks in the playbook directory.

ansible-playbook bigip-newtenant.yml
ansible-playbook bigip-newvip.yml
