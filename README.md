# salesforce
## Setup Salesforce Developer Organisation
URL : https://guirre-dev-ed.my.salesforce.com
Login : mohamed.guirre@secours-islamique.org
Pass : A.....#1111

## The Lightning Design System
URL : https://www.Lightningdesignsystem.com

## SalesForce DX
https://login.salesforce.com/ 
Nom d'utilisateur : mohamed.guirre.sfdx@secours-islamique.org
Pass : A....#1111

## Salesforce DX commands
### auth commands
```
PS C:\Users\guirre.SIFRANCE> sfdx force:auth:web:login -r https://login.salesforce.com
Successfully authorized mohamed.guirre.sfdx@secours-islamique.org with org ID 00D1t000000rxyTEAQ
You may now close the browser
```
### Setting a default Dev Hub for scratch Org creation
```
PS C:\outils\salesforces\setup_salesforce_dev\salesforce> sfdx force:config:set defaultdevhubusername=mohamed.guirre.sfdx@secours-islamique.org -g
=== Set Config
NAME                   VALUE
─────────────────────  ─────────────────────────────────────────
defaultdevhubusername  mohamed.guirre.sfdx@secours-islamique.org

```

### Creating a new Salesforce DX project
```
PS C:\outils\salesforces\setup_salesforce_dev\salesforce> sfdx force:project:create -n SampleDxProject
target dir = C:\outils\salesforces\setup_salesforce_dev\salesforce
   create SampleDxProject\sfdx-project.json
   create SampleDxProject\README.md
   create SampleDxProject\.forceignore
   create SampleDxProject\config\project-scratch-def.json
``` 
### Creating a scratch Org
```
PS C:\outils\salesforces\setup_salesforce_dev\salesforce> sfdx force:org:create -f ./SampleDxProject/config/project-scratch-def.json -a LightningScratchOrg
Successfully created scratch org: 00D3E0000009cGrUAI, username: test-ftzkfbe40tas@example.com
```

### Opening the scratch Org
```
PS C:\outils\salesforces\setup_salesforce_dev\salesforce\SampleDxProject> sfdx force:config:set defaultusername=test-ftzkfbe40tas@example.com
=== Set Config
NAME             VALUE
───────────────  ─────────────────────────────
defaultusername  test-ftzkfbe40tas@example.com
```

```
PS C:\outils\salesforces\setup_salesforce_dev\salesforce\SampleDxProject> sfdx force:org:open -u test-ftzkfbe40tas@example.com
Access org 00D3E0000009cGrUAI as user test-ftzkfbe40tas@example.com with the following URL: https://app-power-5391.cs82.my.salesforce.com//secur/frontdoor.jsp?sid=00D3E0000009cGr!AR8AQOy2De8Wbodg72GyETr3HOyn3yFX
dmD0o8KTPHuKea_oYUXN4gd8OFhkxPxtw7O.LtaHnxlJmidEZZi7f.q09xOZPPDI
```

### Pulling source from a scratch Org
```
PS C:\outils\salesforces\setup_salesforce_dev\salesforce\SampleDxProject> sfdx force:source:pull
=== Pulled Source
No results found
```

```
sfdx force:org:open -u test-ftzkfbe40tas@example.com
```

```
PS C:\outils\salesforces\setup_salesforce_dev\salesforce\SampleDxProject> sfdx force:source:pull
=== Pulled Source
STATE  FULL NAME                TYPE                  PROJECT PATH
─────  ───────────────────────  ────────────────────  ────────────────────────────────────────────────────────────
Add    HelloWord\HelloWord.cmp  AuraDefinitionBundle  force-app\main\default\aura\HelloWord\HelloWord.cmp-meta.xml
Add    HelloWord\HelloWord.cmp  AuraDefinitionBundle  force-app\main\default\aura\HelloWord\HelloWord.cmp
```

### Push source code to a scratch Org
```
PS C:\outils\salesforces\setup_salesforce_dev\salesforce\SampleDxProject> sfdx force:source:push
=== Pushed Source
No results found
```
```
PS C:\outils\salesforces\setup_salesforce_dev\salesforce\SampleDxProject> sfdx force:source:push -f
=== Pushed Source
STATE    FULL NAME                TYPE                  PROJECT PATH
───────  ───────────────────────  ────────────────────  ───────────────────────────────────────────────────
Changed  HelloWord\HelloWord.cmp  AuraDefinitionBundle  force-app\main\default\aura\HelloWord\HelloWord.cmp
```