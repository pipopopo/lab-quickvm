vms
=========

The role vms has the purpose of pulling the RHEL images from Red Hat and creating VMs from those images.

Requirements
------------

- You need to have a KVM host on which to deploy the VMs
- You need to have credentials for Red Hat Portal and generate an [offline token](https://access.redhat.com/management/api)
- The role is meant to be run against a KVM host

Role Variables
--------------
- version 
  - The RHEL version for the image you want to pull from the Red Hat Portal
- arch
  - Which architecture for the image you pull from the Red Hat Portal 
- offline_token
  - This is the offline token you generated on the Red Hat Portal
- downloads
  - The directory into which the images will be stored
- password
  - The password that will be injected into the image
- key 
  - the ssh key that will be injected into the image
- clients
  - A list of vms to be deployed
- memory
  - How much memory the vms should have
- vcpu
  - How many vcpu the vms should have
- disk_size
  - What should be the disk size for the vms
- domain
  - The domain name for the hostname of the vms
  
Dependencies
------------

None

Example Playbook
----------------

    ---
    - hosts: localhost
    gather_facts: yes
    become: yes
    remote_user: root
    roles:
      - vms
   
License
-------

BSD

Author Information
------------------
- Linkedin: <https://www.linkedin.com/in/kenny-tordeurs-4326ab16>
- Name: Kenny Tordeurs 
- Email: ktordeur@redhat.com
