


## run
```bash

#bootstrap main machine
debops bootstrap -l cloud_main

#setup main machine
debops -l cloud_main

#start lxc containers
debops ansible/playbooks/lxc.yml

# bootstrap lxc containers
debops bootstrap --limit lxc

# setup all services
debops

# extra playbooks
debops ansible/playbooks/prometheus.yml
```
