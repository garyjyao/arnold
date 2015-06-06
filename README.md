# Arnold

Some orchestration tasks for Arnold.

# INSTALL

1. Checkout __code__
    ```git clone git@github.com:garyjyao/arnold.git```

2. Setup working environment:
    * __OSX__:
        1. Install Xcode
        2. sudo easy_install pip
        3. sudo pip install ansible

3. Ssh Key
    * ensure your private is able to login to all hosts as ec2-user(optional as yourself)

4. Run playbook from the top level of code to have inventory file as default
    * test connectivity against all hosts: ansible *arnold* -m ping -u ec2-user
    * stop all arnold apps in aws2 environment: ansible-playbook playbooks/stop_apps.yml -e target=aws2_arnold
    * start all arnold apps in aws2 environment: ansible-playbook playbooks/start_apps.yml -e target=aws2_arnold    
    * stop all tramada apps in aws2 environment: ansible-playbook playbooks/stop_apps.yml -e target=aws2_tramada
    * update all tramada hosts in aws2 environment: ansible-playbook playbooks/yum_update.yml -e target=aws2_tramada
    * reboot all tramada hosts in aws2 environment: ansible-playbook playbooks/reboot.yml -e target=aws2_tramada
    * start all tramada hosts in aws2 environment: ansible-playbook playbooks/start_apps.yml -e target=aws2_tramdada
    * also support 1 & 3, partially support 4
    * also support cwt & uos