# Flex Kafka

Flexible setup to experiment with kafka.

## VirtualBox creating new base box for vagrant

### Ubuntu

Create a VirtualBox image (create box, attach iso, install).  To get some
base stuff available (sudo apt-get install ssh) install it now.  Select
"Devices/Insert Guest Addtions CD", this will request to be autorun.  Do
a restart.

Following (partly):
https://github.com/ckan/ckan/wiki/How-to-Create-a-CentOS-Vagrant-Base-Box



### CoreOS

## CoreOS

https://coreos.com/docs/

https://coreos.com/os/docs/latest/booting-on-vagrant.html

- VirtualBox create a base box
  - linux; other linux 64 bit
  - select coreos iso and boot; land in a prompt
  - 'sudo passwd core' to add a password to this acct
  - set up port forwarding to the host
  - scp -P <ssh port chosen> cloud-config.yml core@localhost:
  - validate cloud-config with coreos-cloudinit --validate --from-file cloud-config.yaml
  - sudo coreos-install -d /dev/sda -C stable -c ~/cloud-config.yaml
     will download fresh image
  - sudo halt
  - remove iso image from the box (Storage Remove)
  - boot; passwords don't seem to be set correctly
