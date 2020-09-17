### Introduction to Azure Policy

Azure Policy is the set of rules we can enforce over azure resources .

> an Organisation need to make sure all their Azure resources are deployed under west us region.

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
