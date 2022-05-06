# Ansible Role - pm2

Install and configure PM2 for a nodejs project

Available on Ansible Galaxy: [isaackehle.pm2](https://galaxy.ansible.com/isaackehle/pm2)

## Variables

```yaml
vars:
  flags:
    - init # Basic initialization
    - processes # Configure the node processes to start at reboot
    - upgrade # Upgrade relevant packages

  deploy_dir: # Required for where the base path lives
```

## Examples

```yaml
- hosts: all

  roles:
    - { role: isaackehle.pm2, flags: ["init"] }
    - { role: isaackehle.pm2, flags: ["processes"] }
    - { role: isaackehle.pm2, flags: ["upgrade"] }
```

```bash
export deploy="'deploy_dir': '/opt/servers/node'"

ansible-playbook playbooks/pm2.yml -e "{'flags': ['init'], ${deploy }}" -t init
ansible-playbook playbooks/pm2.yml -e "{'flags': ['configure'], ${deploy }}" -t processes
ansible-playbook playbooks/pm2.yml -e "{'flags': ['packages'], ${deploy }}" -t upgrade
```

## Linting

```bash
yamllint -c yamllint.yaml .
ansible-lint .
```

## License

MIT

## Author Information

Isaac Kehle
@isaackehle ([twitter](https://twitter.com/isaackehle), [github](https://github.com/isaackehle), [linkedin](https://www.linkedin.com/in/isaackehle))

### References

- [PM2 Home](https://pm2.io/doc/en/runtime/overview/)
