Role Name

A brief description of the role goes here.
=======
Jenkins-Slave-Setup
=========

A role to set up the Jenkins slave.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.
Inside of files, have the public key of your Jenkins master copied in the file "authorized_keys."

In addition, if you ever want to add a new password, please use the following command:

```ansible all -i localhost, -m debug -a "msg={{ '<your-password>' | password_hash('sha512', 'mysecretsalt') }}"```

to generate your hashed passwords, or else logging in will cause Ansible to think your variables is a hash and give you two conflicting password. This is why most folks were having issues with "password incorrect" error.

Role Variables
--------------
| Variable Name         | Default value                                                                                          |
|-----------------------|--------------------------------------------------------------------------------------------------------|
| jenkins_password      | $6$mysecretsalt$MIJffjeQyfrKKrGkprGrDL/g2mCJa53koLmYQuuLmY9y37pDvGKPXU1Ov3RbMi.tpQ9cWvxAzUVtBLe7KrZoU. |
| remote_root_directory | /home/jenkins                                                                                          |


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
<<<<<<< HEAD
         - { role: username.rolename, x: 42 }
=======
         - jenkins-slave-setup
>>>>>>> 2236983ea32a51aacbac222dabc2145101787915

License
-------

BSD

Author Information
------------------

<<<<<<< HEAD
An optional section for the role authors to include contact information, or a website (HTML is not allowed).
=======
Author name: Amber Lee

Email: cryptoboxomics@aol.com
>>>>>>> 2236983ea32a51aacbac222dabc2145101787915
