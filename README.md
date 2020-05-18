
Ansible Role for LEMP Stack
======================
An ansible role for deploying LEMP Stack on CentOS/Redhat 7. The role will specifically cover:

 - Installation of MariaDB 10.3 from official repositories, ensuring
   idempotency
 - Installation of PHP 7.4 (or any other PHP version) from Remi
    repository
 - Installation of Nginx from official repositories
 - Creation of a sample user and database for CMS
 
Issues, feature requests, ideas, suggestions, etc. are appreciated and will be readily implemented. If you use/like this role, please consider giving it a star. Thank you!

Requirements
------------

No particular pre-requisite

Role Variables
--------------
|Variable 							|Value 										| Comments
|:--|--|--|
|`mysql_root_password` 				|`somerandom`								| Root password for MariaDB 
|`cms_user_pass`					|`anotherrandom` 							| User password for CMS 
|`mariadb_packages` 				|`mariadb-server` , `mariadb-client` 		| List of MariaDB packages
|`php_packages`						|`php`, `php-mysqlnd` ,`php-fpm` ,`php-cli`	| List of PHP packages

Dependencies
------------
None

Example Playbook
----------------

The role can be easily included in a playbook.

    ---
    - hosts: centos
      become: yes
    
      tasks:
         - name: Use lemp stack role
           include_role:
               name: /home/ansible/playbooks/lemp-stack


Author:
------------------
 [Faizan Younus](https://github.com/ifaizan)
