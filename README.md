Role Name
=========

Provision nodes with KVM. Installs packages and starts services. 

Works for CentOS, Fedora and Ubuntu boxes.

CentOS 8 is not supported. Do no use! https://endoflife.date/centos
Requirements

Fedora 35, 36 and 37 are still actively supported 

fedora releases https://en.wikipedia.org/wiki/Fedora_Linux_release_history

ubuntu releases https://wiki.ubuntu.com/Releases

ubuntu development codenames https://wiki.ubuntu.com/DevelopmentCodeNames


Requirements/Asumptions
------------

none. just ssh


Role Variables
--------------

none

Dependencies
------------

Must have ssh setup. Follow this repo. 


Demo
----

```
ansible-playbook -i inventory test.yml --list-tasks

playbook: site.yaml


playbook: site.yaml

  play #1 (all): all	TAGS: []
    tasks:
      ../../ : set-hostname	TAGS: [hostname, setup]
      ../../ : detect-fedora	TAGS: [detect_os, fedora, os, setup]
      ../../ : detect-centos	TAGS: [centos, detect_os, os, setup]
      ../../ : detect-debian-family	TAGS: [debian, detect_os, os, setup]
      ../../ : update dnf packages, cache	TAGS: [dnf, fedora, setup]
      ../../ : install-dnf-packages	TAGS: [dnf, fedora, setup]
      debug	TAGS: [centos, setup, yum]
      ../../ : epel-release	TAGS: [centos, setup, yum]
      ../../ : update packages, cache, auto clean	TAGS: [centos, setup, yum]
      ../../ : install-yum-packages	TAGS: [centos, setup, yum]
      ../../ : install-dpkg-packages	TAGS: [apt, dpkg, setup]
      ../../ : define-fedora-iso-dir	TAGS: [download, fedora, fedora_iso, iso]
      ../../ : create-dirs-for-fedora-iso-images	TAGS: [dir, download, fedora, fedora_iso, iso, iso_dir]
      ../../ : check-fedora-checksum-file-on-local	TAGS: [checksum, download, fedora, fedora40_checksum, fedora_iso, iso]
      ../../ : get-fedora-checksum-file-from-net	TAGS: [checksum, download, fedora, fedora40_checksum, fedora_iso, iso]
      ../../ : test-fedora-iso-images-on-local	TAGS: [download, fedora, fedora_iso, get_iso, iso]
      ../../ : get-fedora-iso-netinst	TAGS: [download, fedora, fedora_iso, get_iso, iso]
      ../../ : get-fedora-iso-dvd	TAGS: [download, fedora, fedora_iso, get_iso, iso]
      ../../ : define-ubuntu-iso-dir	TAGS: [download, iso, ubuntu_iso]
      ../../ : create-dirs-ubuntu-iso-images	TAGS: [dir, download, iso, iso_dir, ubuntu_iso]
      ../../ : check-ubuntu-checksum-file-on-local	TAGS: [checksum, download, iso, ubuntu24, ubuntu_iso]
      ../../ : get-ubuntu-checksum-file-from-net	TAGS: [checksum, download, iso, ubuntu24_checksum, ubuntu_iso]
      ../../ : test-ubuntu-iso-images-on-local	TAGS: [download, get_iso, iso, ubuntu_iso]
      ../../ : get-ubuntu-live-server-iso	TAGS: [download, get_iso, iso, ubuntu_iso]
      ../../ : define-debian-iso-dir	TAGS: [debian_iso, download, iso]
      ../../ : create-dirs-for-debian-iso-images	TAGS: [debian_iso, dir, download, iso, iso_dir]
      ../../ : check-debian-checksum-file-on-local	TAGS: [checksum, debian12_checksum, debian_iso, download, iso]
      ../../ : get-debian-checksum-file-from-net	TAGS: [checksum, debian12_checksum, debian_iso, download, iso]
      ../../ : test-debian-dvd-iso-images-on-local	TAGS: [debian_iso, download, get_iso, iso]
      ../../ : get-debian-dvd-iso	TAGS: [debian_iso, download, get_iso, iso]
      ../../ : create-dir-for-cloud-images	TAGS: [cloud_dir, cloud_images, dir, download, images]
      ../../ : define-fedora-iso-dir	TAGS: [cloud_images, download, images]
      ../../ : check-fedora-cloud_checksum-kvm-file-on-local	TAGS: [checksum, cloud_images, download, fedora40_checksum, images]
      ../../ : get-fedora-checksum-kvm-file-from-net	TAGS: [checksum, cloud_images, download, fedora40_checksum, images]
      ../../ : test-fedora-cloud-kvm-images-on-local	TAGS: [cloud_images, download, get_kvm_cloud, images]
      ../../ : get-fedora-kvm-cloud-image	TAGS: [cloud_images, download, get_cloud, images]
      ../../ : check-fedora-cloud_checksum-generic-file-on-local	TAGS: [checksum, cloud_images, download, fedora40_checksum, images]
      ../../ : get-fedora-checksum-generic-file-from-net	TAGS: [checksum, cloud_images, download, fedora40_checksum, images]
      ../../ : test-fedora-cloud-generic-images-on-local	TAGS: [cloud_images, download, get_generic_cloud, images]
      ../../ : get-fedora-kvm-cloud-image	TAGS: [cloud_images, download, get_cloud, images]
      ../../ : Get-XML-data-for-iso-image-pool	TAGS: [boxes, kvm, pool, vms]
      ../../ : Get-XML-data-for-cloud-image-pool	TAGS: [boxes, kvm, pool, vms]
      ../../ : create-pool-for-iso-images	TAGS: [boxes, kvm, pool, vms]
      ../../ : create-pool-for-cloud-images	TAGS: [boxes, kvm, pool, vms]
      ../../ : activate-iso-image-pools	TAGS: [boxes, kvm, pool, vms]
      ../../ : activate-cloud-image-pools	TAGS: [boxes, kvm, pool, vms]
      ../../ : status-cloud-image-pools	TAGS: [boxes, kvm, pool, vms]
      ../../ : new-dir-for-kvm-scripts	TAGS: [boxes, kvm, script, vms]
      ../../ : new-dir-for-cloud-init-config	TAGS: [boxes, cloud-init-config, kvm, vms]
      ../../ : upload-kick-fedora-vm-script	TAGS: [boxes, kvm, script, vms]
      ../../ : upload-cloud-init-meta-data	TAGS: [boxes, kvm, script, vms]
      ../../ : upload-cloud-init-user-data	TAGS: [boxes, kvm, script, vms]
      ../../ : upload-kick-fedora-with-cloud-init-script	TAGS: [boxes, kvm, script, vms, x0]
      ../../ : upload-non-root-ssh-key	TAGS: [boxes, kvm, kvm_ssh_key, ssh, ssh_key, vms]
      ../../ : enable-services	TAGS: [service, setup, srv]

-------

BSD

Author Information
------------------

jayeola@gmail.com
