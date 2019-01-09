# tower-demos
Serves as a basic Ansible Tower demo repo. The backend uses https://raw.githubusercontent.com/ansible/ansible/devel/contrib/inventory/ec2.py to dynamically update the inventory.

## Demo Steps

### AWS Preparation

1. In EC2, add an SSH key profile
2. Create demo instances on the RHEL AMI
3. Tag the instances DEV, PROD, etc
4. If the environment has more than 50 hosts, tag all of them for just the demo to avoid Tower licensing issues e.g. `tower-demo`


### Demo

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
