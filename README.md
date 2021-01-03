# ansible-pullbooks

Experimental scripts to handle baseline configuration and maintenance of servers via `ansible-pull`

## Configuration

Initial configuration of a newly-deployed server is done via the [pull-setup.yml](pull-setup.yml) file. This:

- Installs OS-specific dependencies
- Installs Ansible and Git
- Creates working directory
- Adds a configuration for logrotate
- Configures the cron job

This can be accomplished for one or more remote servers by running the following from your local machine:

```
ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook pull-setup.yml -i comma_separated_ip_list
```

_NOTE_: If running for a single server, a trailing comma is required.

## Testing

- Ensure ansible and git are installed on the test system
- Clone this repo to the target test system
- Update the desired playbook
- Run the following:

```
ansible-playbook local.yml
```
