mockfog_application
=========

Rolls out a ping application and configures it using the hostvars set by mockfog_topology.
The respective playbook is placed in the parent directory.

Tags:
- deploy: roll out and start application, delete priorly running instances and data
- collect: collect logs, keep application running

### Requirements

- needs to be run after mockfog_network
- configure application definition in `vars/application_definition.yml`
- configure application configuration in `vars/application_config.yml`:
    - define how applications should be deployed to the nodes
    - additionally, 
        * define extra parameters like `volume` mounting for docker.
        * optional environmental variables in `env` 

### Role Variables

A playbook needs to be run with the following parameters:
```bash
--key-file=XXXX
--ssh-common-args="-o StrictHostKeyChecking=no"
```

Testbed definition fields are available in a similar fashion as if they were supplied as a vars file (thanks to ec2.py inventory).
