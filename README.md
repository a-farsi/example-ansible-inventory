# example-ansible-inventory

1. Create a cluster (1 ansible and 1 client). 
2. Create a file called 'inventory.ini' file with the following inventory rules:
    -   All hosts via the "all" group should have the admin user as login.
    -   The client should be part of a group called "prod".
    -   The password to use for all ssh connections should be admin for all machines in the "prod" group.
    -   The env variable should be set to 'production' for all machines in the 'prod' group.
3. Create a 'inventory.yaml' file, a YAML version of the ini file. 
4. Test the ping through ad-hoc commands using the two inventory files.


1. We should first change the user from root to admin : 
sudo su admin -

2. the file is called 'inventory.ini'

3. The yaml file equivalent to the inventory.ini file: 

4. Test the ping:
    -   Using the inventory.ini : 
    execute the command : ``` ansible -i inventory.ini all -m ping```

    -   Using the inventory.yml : 
    execute the following command : ``` ansible -i inventory.yml all -m ping```

As we apply the ping module to the client host which is in the prod group, we can replace the 'all' in the command either by 'prod' or 'client'.
So, the command can be written as :
    ``` ansible -i inventory.ini prod -m ping```
    ``` ansible -i inventory.ini client -m ping```

5. Create a file 'myFile.txt' that contains a greeting sentese "Welcome to Ansible {{env}} environment". Then, copy it to the client host using the ansible copy module: 

``` ansible -i inventory.ini copy -a "dest=/home/admin/myFile.txt content='Welcome to Ansible {{env}} environment'"``` 
