# Arnold

Some orchestration tasks for Arnold.

# INSTALL

1. Checkout code:
    ```git clone git@github.com:garyjyao/arnold.git```

2. Setup working environment:
    * __OSX__:
        1. Install Xcode
        2. sudo easy_install pip
        3. sudo pip install ansible

3. Ssh Key Requirement
    * ensure your private key is able to login to all hosts as ec2-user (optional as yourself)

4. Run playbook from the top level of code to have inventory file as default
    * test connectivity against all hosts: 
        ansible *arnold* -m ping -u ec2-user
    * stop/start all arnold apps in aws2 environment: 
        1. ansible-playbook playbooks/stop_apps.yml -e target=aws2_arnold -u ec2-user
        2. ansible-playbook playbooks/start_apps.yml -e target=aws2_arnold -u ec2-user
    * stop/patch/reboot/start all tramada apps in aws2 environment:
        1. ansible-playbook playbooks/stop_apps.yml -e target=aws2_tramada -u ec2-user
        2. ansible-playbook playbooks/yum_update.yml -e target=aws2_tramada -u ec2-user
        3. ansible-playbook playbooks/reboot.yml -e target=aws2_tramada -u ec2-user
        4. ansible-playbook playbooks/start_apps.yml -e target=aws2_tramdada -u ec2-user
    * should works in 1 & 3, doesn't works in 4 (too lazy to define inventory)
    * should works with cwt & uos