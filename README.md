## Create VM(s) from images pulled from Red Hat on KVM
The purpose of this playbook are the following steps:
- Pull a specific RHEL version from the Red Hat portal
- Modify the image and inject a password/ssh-key for root
- Make a copy of the image into /var/lib/libvirt/images for each VM
- Inject the hostname in the image
- Create the VM with default NAT network (option to specify a network interface if needed)
- Enable ip forward on the KVM host so NAT will work

## Sample how to run the playbook
``` ansible-playbook run.yml -K --ask-vault-pass ```