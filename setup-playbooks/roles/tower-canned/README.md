Role Name
=========

Role to set up a proscriptive Ansible Tower/AWX demo.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

```
my_project: 
my_inventory_project: 
my_machine_creds: 
my_machine_key_creds: 
my_inventory: 
my_subscription_creds: 
my_git_creds: 
my_scm_demo_url: 
my_scm_inventory_url: 
my_mssql_password: 
my_default_user: 
my_default_password: 
my_rh_password: 
my_rh_username: 
my_pool_id: 

tower_key: 
tower_pubkey: 

my_tower_config_file: 
my_inventory_file: 

# list of users to add in users.yml
users:
  - username:
    password:
    email:
    firstname:
    lastname:
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
