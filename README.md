# Puppet demo


# Create a docker node 
### create Centos container
`sudo apt-get install openvswitch-switch`
### Add Puppet master hostname
`vi etc/hosts`
`172.17.0.1      mosaic-vm puppet-master`

## Puppet agent
### Install
`rpm -Uvh https://yum.puppet.com/puppet6-release-el-7.noarch.rpm`
`yum install -y puppet-agent`
### test
`sudo lxd init`

### Sign certificate on master

 `puppetserver ca sign --all`
 
