# Project-Deployment

## Pre-requsites
- Get an account of the Melbourne Research Cloud (MRC).
- Login to the MRC and navigate to the settings under Users and reset your password. Save the new password.
- Download the OpenStack RC file under Users. Rename the file to `openrc.sh`
- Put the openrc.sh under `mrc` folder.

## Steps to deploy

### Melbourne Research Cloud Infrastructure 
- Execute `run-mrc.sh`
- Update the IPs in the `inventory/hosts` file

### Common Softwares
- Execute <br> 
`ansible-playbook -i ../inventory/hosts -u ubuntu ./common-software/main.yaml`

### CouchDB Setup
- Execute <br> 
`ansible-playbook -i ../inventory/hosts -u ubuntu ./couchdb/couchdb.yaml`