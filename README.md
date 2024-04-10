# Virtual Hosts + SSL Configuration on nginx webserver by ansible

Ansible is an open source configuration management tool. One of the important tools for devops engineer for robust automation. 

In this project, we will be deploying multiple websites on a single webserver irrespective of the operating system as ansible will auto detect it. 

We have chosen a sample shopping website and a travel website to demostrate virtual host configuration. 

Reference - https://www.free-css.com/

The type of virtual host for the project is <strong>IP-PORT</strong> based. 

We have created self signed certficates as well to deploy the sites securely.

We are using Amazon EC2 instance for the demo. You may also use VM/Linux OS/other cloud providers to test the same.

## Following are the steps:
1. Cloing the repo:

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

3. Configuring ansible to become master-node.

	Edit /etc/ansible/hosts
	```
	[<groupname>]
	<ip> ansible_user=ubuntu ansible_ssh_private_key_file=/home/ubuntu/tech.pem
	```
	2.3 -	Edit the host name in master.yaml file and run 	
	```
	ansible-playbook master.yml
	```
 
4. Go the ec2 ip/localhost and curl:
	```
	curl <ip>:<port>
	```

	```
	curl <ip>:<port>
	```
 5. Assuming the websites are deployed on cloud instances, we can the access the same over internet using the following URLs:
    	```
    	https://<ip>/shop
    	```
    	```
    	https://<ip>/travel
    	```

If you are in connected on a LAN, other systems/computers can ping and browse the website.

Note - If you wish to route the website using domain, make the following changes on your Windows/Linux hosts path:

On Linux - /etc/hosts and add the following lines:

<ip> shop.com

<ip> travel.com

On Windows - C:\Windows\System32\drivers\etc\hosts 

<ip> shop.com

<ip> travel.com

Now, you can easily search http://www.shop.com or http://www.travel.com ( Note - This works on local computer only! This is not hosted over internet )
	
Any recommendations? Ping me on - bhikesh.khute@outlook.com



