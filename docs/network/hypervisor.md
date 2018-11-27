# Hypervisors

Deployment procedure for new hypervisors, and documentation of existing hypervisor configurations.

Hypervisors are intended to be deployed on CentOS 7.5+ systems with a minimum of 8GB of RAM and 120GB of available hard drive space.

I use [Ovirt](https://ovirt.org/) for virtualization, which sits on top of KVM. See the [Ovirt Installation Docs](https://ovirt.org/documentation/install-guide/chap-Installing_oVirt/) for details, but the basic procedure is given below:

1. Temporarily disable the EPEL and IUS repositories so that they don't interfere with Ovirt's installation
   * `sudo mv /etc/yum.repos.d/ius.repo /etc/yum.repos.d/ius.repo.bak`
   * `sudo mv /etc/yum.repos.d/epel.repo /etc/yum.repos.d/epel.repo.bak`
2. Install the Ovirt repository
   * `sudo yum install https://resources.ovirt.org/pub/yum-repo/ovirt-release42.rpm`
   * Increment the filename as new releases are available
3. Ensure all packages are updated with the Ovirt repository
   * `sudo yum update -y`
4. Install the Ovirt engine and KVM
   * `sudo yum install qemu-kvm libvirt libvirt-python libguestfs-tools virt-install ovirt-engine`
5. Re-enable the EPEL and IUS repositories
   * `sudo mv /etc/yum.repos.d/ius.repo.bak /etc/yum.repos.d/ius.repo`
   * `sudo mv /etc/yum.repos.d/epel.repo.bak /etc/yum.repos.d/epel.repo`
6. Configure the Ovirt engine
   * `sudo engine-configure`



