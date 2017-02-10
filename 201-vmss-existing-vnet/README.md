# Deploy a VM Scale Set into an existing vnet

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https://raw.githubusercontent.com/varunpsr/azure-quickstart-templates/master/201-vmss-existing-vnet/azuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https://raw.githubusercontent.com/varunpsr/azure-quickstart-templates/master/201-vmss-existing-vnet/azuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

This template deploys a Windows based VM Scale Set into an existing vnet. To connect from the load balancer to a VM in the scale set, you would go to the Azure Portal, find the load balancer of your scale set, examine the NAT rules, then connect using the NAT rule you want. For example, if there is a NAT rule on port 50000, you could use the following command to connect to that VM:

ssh -p 50000 {username}@{public-ip-address}

PARAMETER RESTRICTIONS
======================

vmssName must be 3-61 characters in length. It should also be globally unique across all of Azure. If it isn't globally unique, it is possible that this template will still deploy properly, but we don't recommend relying on this pseudo-probabilistic behavior.

instanceCount must be 100 or less.
