# Virtual Hosts Configuration In Apache On Different OS Using Ansible

Ansible is an open source configuration management tool. One of the important tools for devops engineer for robust automation. 

In this project, we will be deploying multiple websites on a single webserver irrespective of the operating system as ansible will auto detect it. 

We have chosen a sample shopping website and a travel website to demostrate virtual host configuration. Reference - https://www.free-css.com/

The type of virtual host for the project is # IP-PORT based. 

We are using Amazon EC2 instance for the demo. You may also use VM/Linux OS/other cloud providers to test the same.

## Following are the steps to try it on your own local :D 
1. Cloing the repo:

``` 
git clone bhikeshkhute/Virtual-Hosts-Configuration-In-Apache-On-Different-OS-Using-Ansible
```
2. Installing Ansible:

	2.1 - For Debian/Ubuntu 
	
	```
	sudo apt-get install ansible-core
	```
		 
	2.1 - For RedHat/CentOS 
	
	```
	sudo yum install ansible-core
	```

3. Configuring ansible to become master-node.

	vi /etc/ansible/hosts
	```
	[demo]
	master ansible_user=<osuser> ansible_ip=<privateip> ansible_key=<ifusingec2elseskip>
	```
	2.3 -	Run 	
	```
	ansible-playbook master.yml
	```

4. Go the ec2 ip/localhost and search:

	```
	http://<ip>:8081
	```

	```
	http://<ip>:8082
	```

If you are in connected on a LAN, other systems/computers can ping and browse the website.

Note - We can configure name-based configuration if you are using Linux OS/VM. Do the following changes:

Open - /etc/hosts and add the following lines:

127.0.0.1 shop.com

127.0.0.1 travel.com

Now, you can easily search http://www.shop.com or http://www.travel.com
	
Any recommendations? Ping me on - bhikesh.khute@outlook.com



