### Some [Ansible](https://www.ansible.com) Playbooks and Tasks for [IBM MQ](https://www.ibm.com/products/mq)

Tested on AIX and Red Hat Enterprise Linux

---

Ansible needs to be [installed](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) on the target system.

#### Installation
```
ansible-playbook install_mq.yaml --extra-vars="MQ_FILE_NAME=</path/to/installation/file>"
```

#### Uninstall
```
ansible-playbook uninstall_mq.yaml
```

#### Check configuration
```
ansible-playbook check_config_mq.yaml
```

### Backup QMGR (config and data)
```
ansible-playbook backup_qmgr.yaml --extra-vars="QMGR_NAME=<qmgr name>"
```

### Backup QMGR (config only)
```
ansible-playbook backup_config_qmgr.yaml --extra-vars="QMGR_NAME=<qmgr name>"
```

#### Backup QMGR (data only)
```
ansible-playbook backup_data_qmgr.yaml --extra-vars="QMGR_NAME=<qmgr name>"
```

#### Restore QMGR (config and data)
```
ansible-playbook restore_qmgr.yaml --extra-vars="QMGR_NAME=<qmgr name> QMGR_RESTORE_NAME=<filename>"
```

#### Restore QMGR (config only)
```
ansible-playbook restore_config_qmgr.yaml --extra-vars="QMGR_NAME=<qmgr name> QMGR_RESTORE_NAME=<filename>"
```

#### Restore QMGR (Data only)
```
ansible-playbook restore_data_qmgr.yaml --extra-vars="QMGR_NAME=<qmgr name> QMGR_RESTORE_NAME=<filename>"
```

#### Create keystore and insert cert
```
ansible-playbook cert_management_create.yaml --extra-vars="QMGR_NAME=<qmgr name> CERT_FILE=/path/to/cert [KEYFILE_NAME=keyfile name] [CERT_ALIAS=alias name]"
```

#### Add certificate to keystore
```
ansible-playbook cert_management_add.yaml --extra-vars="QMGR_NAME=<qmgr name> CERT_FILE=/path/to/cert [KEYFILE_NAME=keyfile name] [CERT_ALIAS=alias name]"
```

#### List certificates in the keystore
```
ansible-playbook cert_management_list.yaml --extra-vars="QMGR_NAME=<qmgr name> [KEYFILE_NAME=<keystore name>]"
```

#### Delete certificate from keystore
```
ansible-playbook cert_management_delete.yaml --extra-vars="QMGR_NAME=<qmgr name> CERT_ALIAS=<alias name> [KEYFILE_NAME=<keyfile name>]"
```
