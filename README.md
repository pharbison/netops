## Usage ##
Each playbook will have comments at the top with instructions and variables. 

## Playbooks ##
- bootstrap.yml
- bootstrap-security.yml

---

## bootstrap.yml ##
Runs the bootstrap-security.yml playbook first. Then configures the devices for the following items:
- Set VTP to Transparent
- Remove DNS Resolution
- Configures all access ports except last one with voice_vlan, sticky mac, and portfast
- Sets te1/0/1 and te1/0/2 to trunk ports if they exist
- Set logging synchronous on terminal access
- Setup self healing from BPDUGUARD 
- Setup BPDU Guard as a default option 

## bootstrap-security.yml ##
Configures devices for the following:
- Sync ACL for SSH access with ip_list_url
- Disables builtin web server
- Setup NTP server for accurate time 
- Setup logging to central server 
- Setup TACACS+ for authentication 