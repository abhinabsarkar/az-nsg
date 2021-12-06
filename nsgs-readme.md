# Azure Cache for Redis - NSG rules
```bash
# Get all the NSG securtiy rules (Non-default)
az network nsg show -g <resource-group> -n <nsg-name> --subscription <subscription-name> --query "securityRules" -o table > nsg.txt
# Get all the NSG securtiy rules with "Allow" access. Includes inbound & outbound rules
az network nsg show -g <resource-group> -n <nsg-name> --subscription <subscription-name> --query "securityRules[?access=='Allow']" -o table
# Get all the NSG securtiy rules with "Allow" access & direction as Inbound
az network nsg show -g <resource-group> -n <nsg-name> --subscription <subscription-name> --query "securityRules[?access=='Allow'&&direction=='Inbound']" -o table
```

```bash
# List the NSGs for Redis Cache for a subscription
az network nsg list --subscription <subscription-name> -o table | grep redis
# Get the security rules for the NSGs listed
az network nsg show -n <nsg-name> -g <resource-group> --subscription <subscription-name> --query "securityRules" -o table > nsg.txt

# List the NSGs for Redis Cache for a subscription
az network nsg list --subscription <subscription-name> -o table | grep redis

# Get the security rules for the above mentioned NSGs
az network nsg show -n <nsg-name> -g <resource-group> --subscription <subscription-name> --query "securityRules" -o table > nsg.txt
```