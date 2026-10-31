# ansible

Ansible playbooks and roles from hands-on practice: installing packages, running shell commands locally and on a remote host, and deploying an ELK stack. This is a lab/learning project.

## Contents
| Path | What it covers |
|---|---|
| [playbooks](./playbooks) | `install_packages.yml`, `run_shell_commands.yml` (localhost), `run_shell_commands_remote.yml` (remote host) |
| [inventory](./inventory) | Example inventory in INI (`hosts.ini`) and YAML (`hosts.yaml`) formats |
| [elk_stack](./elk_stack) | Roles to deploy Java, Elasticsearch, Kibana, nginx and Logstash on CentOS |
| [testfolder](./testfolder) | Sample output of the shell-command playbooks (see its `README.txt`) |

## Structure
```text
.
├── inventory/
│   ├── hosts.ini
│   └── hosts.yaml
├── playbooks/
│   ├── install_packages.yml
│   ├── run_shell_commands.yml
│   └── run_shell_commands_remote.yml
├── elk_stack/
│   ├── elk_playbook.yml
│   ├── hosts.ini
│   └── roles/            # java, elasticsearch, kibana, nginx, logstash
└── testfolder/           # output of the shell-command playbooks
```

## Usage
```bash
# Run a playbook on the remote host from the inventory
ansible-playbook -i inventory/hosts.ini playbooks/run_shell_commands_remote.yml

# Deploy the ELK stack
cd elk_stack
ansible-playbook -i hosts.ini elk_playbook.yml
```

## File naming
File names use underscores, not hyphens. Names with hyphens did not work well with tab completion on the command line, so they were renamed.

| Original name | Current name |
|---|---|
| `installpackages_ansbl.yaml` | `playbooks/install_packages.yml` |
| `useshell_ansbl.yaml` | `playbooks/run_shell_commands.yml` |
| `useshellremote_ansbl.yaml` | `playbooks/run_shell_commands_remote.yml` |
| `elk_stack/elk_main.yml` | `elk_stack/elk_playbook.yml` |
| `hosts.ini`, `hosts.yaml` | `inventory/hosts.ini`, `inventory/hosts.yaml` |

## Notes
- Targets CentOS hosts (the playbooks use `yum`)
- Server IP addresses are partially masked with `xx` (for example `18.218.xx.xx`). Use your own hosts.
- The SSH private key (`.pem`) is not part of this repository and is excluded in `.gitignore`
- `elk_playbook.yml` runs the `java`, `elasticsearch`, `kibana` and `nginx` roles. The `logstash` role is commented out.
