fcrepo_vagrant
==============

This vagrant machine is a Centos/7 machine with fedora commons repository. This will require an ansible control machine with vagrant and virtualbox.

To clone:

```
git clone --recursive https://github.com/UM-AMC-ACD/fcrepo_vagrant.git
```
To change versions or other defaults:
* Look in the fedora_commons/defaults/main.yml and see the README.md in the fedora_commons directory

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
https://atlas.hashicorp.com/UM-AMC-ACD/boxes/centos7fcrepo as a new version
