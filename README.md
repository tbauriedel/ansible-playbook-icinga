# Ansible Icinga-Stack

Simple Ansible playbook to install the icinga-stack.  
The following componentes will be installed:  
* InfluxDB2
* Go-carbon
* Carbonapi
* Grafana
* MySQL
* Apache
* Icinga repos
* IcingaDB redis
* IcingaDB
* Icinga 2
* Icinga Web 2

Pre-configured credentials:
* InfluxDB primary user
  * Basic auth `admin` - `admin0815!`
* InfluxDB API admin token
  * `admin0815!`
* Grafana admin user
  * Basic auth `admin` - `admin`
* MySQL root user
  * Basic auth `root` - `root`
* Icinga 2 API
  * Basic auth `admin` - `admin`
* Icinga Web 2
  * Basic auth `icinga` - `icinga`

## Usage

**Prepare Inventory**  
Update the inventory to your needs.

**Create Virtual Environment**
```
python3 -m venv .ansible2.9
source .ansible2.9/bin/activate
python3 -m pip install --upgrade pip
python3 -m pip install ansible==2.9
python3 -m pip install passlib bcrypt
ansible-galaxy install -r requirements.yml --force
```

**Deploy Ansible**
```
ansible-playbook -i inventory playbook.yml
```
