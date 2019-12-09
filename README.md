# tower-demos
Serves as a basic Ansible Tower demo repo.

## Demo Steps

### AWS Preparation

1. In EC2, add an SSH key profile
2. Create demo instances on the RHEL AMI
3. Tag the instances DEV, PROD, etc
4. If the environment has more than 50 hosts, tag all of them for just the demo to avoid Tower licensing issues e.g. `tower-demo`


### Demo1

1. Prepare the demo by adding the AWS credentials and an ssh key for host access beforehand.
    1. Walk through adding AWS creds
2. Create a Project for the demo.
    1. Enter `https://github.com/CorwinBurton/tower-demos` for the Git SCM URL
    2. Check all three cleanup boxes and hit save
    3. Show the permissions tab and talk about RBAC
    4. Hit the sync icon on the bottom of the page
3. Go to the Inventories tab and create a new Inventory
    1. Give it a name and hit save
    2. In the sources tab, add a new EC2 source using the AWS credentials
    3. Select a region
    4. If necessary, use the tag created earlier as an instance filter e.g. `tag-key=tower-demo`
    5. Group by key name, tags
    6. Hit sync to retrieve host information
4. Add Job templates - either from the project or the Templates tab on the left
    1. Select the demo inventory, project, etc
    2. Select the list-updates playbook
    3. Select the ssh credential already set up
    4. Enable privilege escalation
    5. Launch the job to show a list of updates
5. Repeat showing the update playbook for just tag_DEV, etc
    1. Limit to tag_DEV

### Demo2
1. Create EC2 instances with the correct tag
2. Sync the inventory
3. Run the bootstrap playbook to install python
4. Run to attach the RHEL instance (may need to remove existing AWS repos if using an Amazon AMI)
5. Deploy httpd with sample web page

## Resources
- [Ansible EC2 Dynamic Inventory](https://docs.ansible.com/ansible/latest/user_guide/intro_dynamic_inventory.html#inventory-script-example-aws-ec2)
- [Ansible Yum Module](https://docs.ansible.com/ansible/latest/modules/yum_module.html)
- [Ansible Subscription-Manager Module](https://docs.ansible.com/ansible/latest/modules/redhat_subscription_module.html)
