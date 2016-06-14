fcrepo_vagrant
==============

This vagrant machine is a Centos/7 machine with fedora commons repository 


To package:
* Remove any hanging syncs and ansible pieces, and clear the unused space

```
vagrant ssh
rm -rf /vagrant /home/vagrant/.ansible
cat /dev/zero > zero.fill;sync;sleep 1;sync;rm -f zero.fill
exit
```
* Package the machine

vagrant package

* Upload the resulting export to:
https://atlas.hashicorp.com/UM-AMC-ACD/boxes/centos7tcjava as a new version
