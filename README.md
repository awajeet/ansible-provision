
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
