### Introduction to Azure Policy

Azure Policy is the set of rules we can enforce over azure resources .

> An Organisation need to make sure all their Azure resources are deployed under west us region.
> Restrict disk size between 4 - 64 GB to prevent cost 
> Restrict developer to create Virtual Machine with sku's B1s , B1ls

It can prevent the creation of disallowed resources, ensure new resources have specific settings applied .

Azure policy is basically 3 components; policy definition , assignment and parameters.

### Azure Policy Defination 

Policy defination is set of logical expression (What to evaluate and what action needs to be taken)

```sh
{
         "if": {
            "allOf": [
               {
                  "field": "type",
                  "equals": "Microsoft.Compute/virtualMachines"
               },
               {
                  "not": {
                     "field": "Microsoft.Compute/virtualMachines/sku.name",
                     "in": "[parameters('listOfAllowedSKUs')]"
                  }
               }
            ]
         },
         "then": {
            "effect": "Deny"
         }
      }
```

### How to create custom Azure Policy

In This Example , We will create a policy to allow  the use of Disk size with 4 GB , 8 GB , 16 GB , 32 GB , 64 GB

```sh
Home > Policy > Policy Defination
```

```sh
{
  "mode": "All",
  "policyRule": {
     "if": {
         "not" :{
              "field": "Microsoft.Compute/disks/diskSizeGB",
              "in": "[parameters('listOfAlloweddiskSize')]"
               }
    },
    "then": {
      "effect": "deny"
    } 
  },
  "parameters": {
    "listOfAlloweddiskSize": {
      "type": "Array",
      "metadata": {
        "description": "The list of allowed disk size for resources.",
        "displayName": "Allowed disk size"
      }
    }
  }
}
```

![](Images/Policy-Step1.png)
### How to assign on azure resource group or Azure Subscription

```sh
Home > Policy > Assign Policy
```
![](Images/Policy-Step2.png)

![](Images/Policy-Step3.png)

### How to test 

Create disk of size 1024 GB . It will raise error while deploying 


