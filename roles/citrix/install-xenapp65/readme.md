# Install Active Directory Directory Services (ADDS)

## Overview

Installs the Windows features required for ADDS

## Requirements
Works on Microsoft Windows operating systems

## Module used
Ansibe module **win_feature**

## Variables
|parameter|required|default|choices|comments|
|---|---|---|---|---|
|include_management_tools|no| |<ul><li>True</li><li>False</li></li>|Adds the corresponding management tools to the specified feature. Not supported in Windows 2008. If present when using Windows 2008 this option will be ignored.|
|include_sub_features|no| |<ul><li>True</li><li>False</li></li>|Adds all subfeatures of the specified feature|
|name|yes|||Names of roles or features to install as a single feature or a comma-separated list of features|
|restart|no||<ul><li>True</li><li>False</li></li>|Restarts the computer automatically when installation is complete, if restarting is required by the roles or features installed.|
|source|no||<ul><li>{driveletter}:\sources\sxs</li><li>{IP}\Share\source\sxs</li></li>|Specify a source to install the feature from.Not supported in Windows 2008. If present when using Windows 2008 this option will be ignored.|
|state|no|present|<ul><li>present</li><li>absent</li></li>|State of the features or roles on the system|


## Examples

```
---
    - name: Install the ADDS and DNS Roles
      win_feature:
        name: "AD-Domain-Services,dns"
        state: present
        include_management_tools: yes
        include_sub_features: yes
```

## License
Proprietary or whatever license from source OSS role this role is based upon.

## Author Information
This role is maintained by: Datacom Systems (Wellington) Limited
Team: UDM
Contact Name:
Contact E-mail:
Contact Phone:
