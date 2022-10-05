# Elastic-AKS-Assets
 
Set APM policy to listen to `0.0.0.0:8200` from `localhost:8200`


Create a static IP for the loadBalancer.

Get Resource Group for AKS
```az aks show --resource-group sunmanAksRsGroup --name sunmanaks --query nodeResourceGroup -o tsv```

That returns a group group.  Use it to create a public IP, which is used in the apm service
az network public-ip create \
    --resource-group `resource group returned by previous command` \
    --name elastic-apm \
    --sku Standard \
    --allocation-method static