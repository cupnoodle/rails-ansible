# Rails Ansible

Note: Storing secret in plaintext in playbook isn't a good practice, I have written this originally for absolute beginner to DevOps. If you are using this on production, I would advise look into using secrets management, like Ansible vault : https://docs.ansible.com/ansible/latest/user_guide/vault.html



Here's an introductory guide on using ansible vault  

To encrypt your environment vars, you can use the `ansible-vault encrypt` command like this :  
`ansible-vault encrypt vars/envs.yml vars/vars.yml`



You can view the content of the encrypted files like this :  
`ansible-vault view vars/envs.yml vars/vars.yml`



When running playbook with encrypted file, you need to provide the password you used to encrypt the file.
You can use `--ask-vault-pass` to supply the vault password at runtime, a prompt will appear for you input the password.  
`ansible-playbook server-provision.yml --ask-vault-pass`




### About

Note: This Ansible script is for Ubuntu 20.04 LTS server.
This Ansible script will setup a server with the following components

1. Ruby
2. Nginx web server
3. Passenger app server
4. PostgreSQL
5. Sidekiq (Optional)


To learn how to use this script, refer to this post : [https://rubyyagi.com/rails-deploy-automate-ansible/](https://rubyyagi.com/rails-deploy-automate-ansible/)