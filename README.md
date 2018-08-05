
Pre-requisites:
Azure Subscription
VM having Azure SDK/Python/Ansible/Azure CLI
Configured Service Principal on VM to interact with Azure.
The filename  ~/.azure/credentials has entry of credentials generated during Service Principal.

cat <<EOF > ~/.azure/credentials
[default]
subscription_id=1234-1234-1234-1234
client_id=11111111-1111-1111-1111-111111111111
secret=secretpassword
tenant=1234567-123456-123456-123456
EOF


Create a pair of private/public keys for azureuser


Provision a new VM:

we have Ansible up and running on VM.
Connect to VM from Terminal. Run ssh azureuser@40.117.79.111

azureuser@myVM:~$ cd ansible-provision/

You will find a playbook to provision a VM in Azure.
ansible-playbook provision_newvm.yml --extra-vars "vmname=azurevmaw resgrp=myResourceGroup vnet=myVnet subnet=mySubnet"

vmname: Name of VM to be given. Here we used azurevmaw.


We have another playbook to change the configuration which calls and runs the subsequent roles and their tasks. 

azureuser@myVM:~/ansible-provision$ ansible-playbook -i azure_rm.py playbookazure.yml --extra-vars  "vmname=azurevmaw"
