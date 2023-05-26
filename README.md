# Project-Deployment

## Pre-requsites
- Get an account of the Melbourne Research Cloud (MRC).
- Login to the MRC and navigate to the settings under Users and reset your password. Save the new password.
- Download the OpenStack RC file under Users. Rename the file to `openrc.sh`
- Put the openrc.sh under `mrc` folder.

## Steps to deploy

### Melbourne Research Cloud Infrastructure 
- Execute `sh ./1.mrc/run-mrc.sh`
- Update the IPs in the `inventory/hosts` file

### Common Softwares
- Execute <br> 
`ansible-playbook -i ../inventory/hosts -u ubuntu ./2.common-software/main.yaml`

### CouchDB and HAProxy Setup
- Execute <br> 
`ansible-playbook -i ../inventory/hosts -u ubuntu ./3.couchdb/main.yaml`

### Mastodon Harvester Setup
- Execute <br>
`ansible-playbook -i ../inventory/hosts -u ubuntu ./4.mastodon-harvester/main.yaml`

### Backend Setup
- Execute <br>
`ansible-playbook -i ../inventory/hosts -u ubuntu ./5.backend/main.yaml`

### Frontend Setup
- Execute <br>
`ansible-playbook -i ../inventory/hosts -u ubuntu ./6.frontend/main.yaml`
