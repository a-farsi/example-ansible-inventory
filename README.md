# example-ansible-inventory

- Create a cluster (1 ansible and 1 client). 
- Create a host.ini file with the following inventory rules:
	-   All hosts via the "all" group should have the admin user as login.
	-   The client should be part of a group called "prod".
	-   The password to use for all ssh connections should be admin for all machines in the "prod" group.
	-   The env variable should be set to "production" for all machines in the "prod" group.
- Create a hosts.yaml file, a YAML version of the ini file. 
- Test the ping setup ad-hoc commands using the two inventory files.