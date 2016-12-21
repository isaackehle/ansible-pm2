# Ansible: pm2

Install and configure PM2 for a nodejs project

Available on Ansible Galaxy: [pgkehle.pm2](https://galaxy.ansible.com/pgkehle/pm2)


## Variables
```yaml
deploy_dir:     Required for where the base path lives
```

## Tags

    core:   PM2 core module
    logs:   pm2-logrorate
    
## Examples

```YAML

  - hosts: all
  
    roles:
      - { role: pgkehle.pm2 }
```

## License

MIT

## Author Information

Paul Kehle  
@pgkehle ([twitter](https://twitter.com/pgkehle), [github](https://github.com/pgkehle), [linkedin](https://www.linkedin.com/in/pgkehle))

### References

* https://futurestud.io/tutorials/pm2-utility-overview-installation