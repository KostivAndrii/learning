Ansible role to setup and configure Jenkins + separated Java role in dependencies.

In Role Default Variables it's possible to change/set:

   **jenkins_admin_username**
   
   **jenkins_admin_password**
   

Password for jenkins admin user stored in $ANSIBLE_VAULT - you should set your own password with or without VAULT.

To run this playbook you should setup 2 VM with present Vagrantfile and run playbook.yml with keys

>   --ask-vault-pass
   
or 

>   --vault-password-file=~/.passfile




Java role can be configured to install JDK **offline** - to do this:
 
1. You can change JDK version to install in java/vars/main.yml variables:

>   offline_jdk_version: 201


1. And you should place in folder role/java/files appropriate version JDK archive file:

>      jdk-8u201-linux-x64.tar.gz

Also Java role able to online install JDK 1.8 or 1.7 into RedHat or Debian family Linux.

To do this necessarily pass to role appropriate variables:

>  - role: java
>  
>      vars:
>      
>        online_jdk: true
>        
>        online_jdk_version: 8

