# Palo_Alto_Backups
Peforms backups of Palo Alto Firewalls and generates HTML diff reports, which will be emailed to specified email addresses.

Saves the configs in backup location defined in ```configs_dir``` in the palo_vars.yml file. (default is /ansible_backups/palo_alto/<date>)

Need to update SSH credentials in palo_vars.yml.

If using AWX/Tower, create a custom credential type as follows. You can then create your credential object using the custom credential type, and fill in your username/password, which will be injected into the API calls. 

Name: Whatever you want
Description: Whatever makes sense

Input Configuration:
```
fields:
  - id: palo_username
    type: string
    label: Username
  - id: palo_password
    type: string
    label: Password
    secret: true
required:
  - username
  - password
```
Injector Configuration:
```
extra_vars:
  palo_password: '{{palo_password}}'
  palo_username: '{{palo_username}}'
```

Modify SED commands as approprate in your environment to cleanup dynamic lines in your configuration files, that you don't want included in the diffs.
