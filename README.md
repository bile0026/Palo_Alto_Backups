# Palo_Alto_Backups
Peforms backups of Palo Alto Firewalls and generates HTML diff reports, which will be emailed to specified email addresses.

Saves the configs in backup location defined in ```configs_dir``` in the palo_vars.yml file. (default is /ansible_backups/palo_alto/<date>)

Need to update SSH credentials in palo_vars.yml.

Modify SED commands as approprate in your environment to cleanup dynamic lines in your configuration files, that you don't want included in the diffs.
