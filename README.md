# Ansible-Role: acr-ansible-keepassxc

AIT-CyberRange: Installs and configures keepassxc and its firefox extension.
It also adds a script that automatically unlocks the database on login. 


## Requirements

- Debian or Ubuntu
- firefox

## Role Variables

```yaml
keepass_user: ubuntu
keepass_database: /home/{{ keepass_user }}/.keepass_db
keepass_password: secret
keepass_xpi_url: https://addons.mozilla.org/firefox/downloads/file/4342010/keepassxc_browser-1.9.3.xpi
keepass_unlock_script_location: /home/{{ keepass_user }}/

keepass_entries:
  - entry_name: entry1
    username: email@example.com
    password: supersecret
    notes: some notes
    url: www.example.com
```

## Example Playbook

```yaml
- hosts: all
  roles:
    - acr-ansible-keepassxc
      vars:
        keepass_user: ubuntu
        keepass_password: secret
        keepass_entries:
          - entry_name: entry1
            username: email@example.com
            password: supersecret
            notes: some notes
            url: www.example.com
```

## License

GPL-3.0

## Author

- Lenhard Reuter