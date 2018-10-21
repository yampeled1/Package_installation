# Package_installation
An Ansible playbook installing a desired package and includes service check

## Prerequisites

- Ansible installed on master server
- Ansible superuser privileges on target server
- *At this case Jenkins repos installed at target server

### Output example

A short example of an output

```
[ansible@yamp playbooks]$ ansible-playbook pkg_installation.yaml 
[DEPRECATION WARNING]: DEFAULT_SUDO_USER option, In favor of Ansible Become, which is a generic 
framework. See become_user. , use become instead. This feature will be removed in version 2.8. 
Deprecation warnings can be disabled by setting deprecation_warnings=False in ansible.cfg.

PLAY [centos] ***************************************************************************************

TASK [Gathering Facts] ******************************************************************************
ok: [yamp2.mylabserver.com]

TASK [Install the indicated software] ***************************************************************
changed: [yamp2.mylabserver.com]

RUNNING HANDLER [start_service] *********************************************************************
changed: [yamp2.mylabserver.com]

PLAY RECAP ******************************************************************************************
yamp2.mylabserver.com.mylabserver.com   : ok=3    changed=2    unreachable=0    failed=0   

** Running again the playbook to check if it restarting the service although it already started

[ansible@sagivzs5 playbooks]$ ansible-playbook pkg_installation.yaml 
[DEPRECATION WARNING]: DEFAULT_SUDO_USER option, In favor of Ansible Become, which is a generic 
framework. See become_user. , use become instead. This feature will be removed in version 2.8. 
Deprecation warnings can be disabled by setting deprecation_warnings=False in ansible.cfg.

PLAY [centos] ***************************************************************************************

TASK [Gathering Facts] ******************************************************************************
ok: [sagivzs6.mylabserver.com]

TASK [Install the indicated software] ***************************************************************
ok: [sagivzs6.mylabserver.com]

PLAY RECAP ******************************************************************************************
sagivzs6.mylabserver.com   : ok=2    changed=0    unreachable=0    failed=0   

** There is 0 changes meaning the service has not been started again

```

## Built With

* [Bash](https://www.gnu.org/software/bash/) - The GNU Project's shell
* [Ansible](https://www.ansible.com/) - Simple, agentless IT automation
* [Jenkins](https://jenkins.io/) -  open source automation server provides support for building, deploying and automating any project.

## Versioning

Untill this point there is only ver 1.0

## Authors

* [Yam Peled](https://github.com/yampeled1)
