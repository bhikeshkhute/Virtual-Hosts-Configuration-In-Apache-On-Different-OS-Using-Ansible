# Virtual Hosts + SSL Configuration on nginx webserver

Ansible is an open source configuration management tool. One of the important tools for devops engineer for robust automation. 

In this project, we will be deploying multiple websites on a single webserver irrespective of the operating system as ansible will auto detect it. 

We have chosen a sample shopping website and a travel website to demostrate virtual host configuration. 

Reference - https://www.free-css.com/

The type of virtual host for the project is <strong>IP-PORT</strong> based. 

We have created self signed certficates as well to deploy the sites securely.

We are using Amazon EC2 instance for the demo. You may also use VM/Linux OS/other cloud providers to test the same.

<p align="center">
      <img src="https://github.com/norfluxX/VHost-Management-with-Ansible/assets/35907619/d21134d3-d12f-4fb0-a8d3-f91defc87802" />
</p>

## Following are the steps:
1. Cloning the repo:

	``` 
	git clone https://github.com/norfluxX/VHost-Management-with-Ansible.git
	```
2. Installing Ansible:

	2.1 - For Debian/Ubuntu 
	
	```
	sudo apt-get install ansible
	```
		 
	2.1 - For RedHat/CentOS 
	
	```
	sudo yum install ansible-core
	```

3. Configuring ansible to become master-node and performing variable changes.

	3.1 - Edit /etc/ansible/hosts
	```
 	[groupname]
 	ipaddress ansible_user=ubuntu ansible_ssh_private_key_file=/home/ubuntu/tech.pem
	```

 	3.2 - Go to ubuntu and redhat folder and traverse to vars folder and find the main.yaml file. Make necessary changes according to your requirement:
   	```
	first_website_name: shop

	second_website_name: travel

	codelocation_one: https://www.live/shop.zip

	codelocation_two: https://www.live/travel.zip
   	```

   	3.3 - Run the playbook	
	```
 	ansible-playbook master.yml
	```
 
 	3.4 - Optional - Run this command to reset everything that was configured by playbook	
	```
	ansible-playbook reset_master.yml
	```
 
5. Go the ec2 ip/localhost and curl:
	```
	curl <ip>:<port>
	```

	```
	curl <ip>:<port>
	```
 6. Assuming the websites are deployed on cloud instances, we can the access the same over internet using the following URLs:
    
    	https://ipaddress/shop/

	```
	https://ipaddress/travel/
 	```
	
Any recommendations? Ping me on - bhikesh.khute@outlook.com



