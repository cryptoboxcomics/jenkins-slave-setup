Jenkins-Slave-Setup
=========

A role to set up the Jenkins slave.

Requirements
------------

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

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
