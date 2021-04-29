# Puppet demo


# Create a docker node 
### Create Centos container
`sudo docker run --name webserver --hostname webserver -ti centos`

`sudo docker run --name server1 --hostname server1  -it -d  --tmpfs /tmp --tmpfs /run --tmpfs /run/lock -v /sys/fs/cgroup:/sys/fs/cgroup:ro jrei/systemd-ubuntu`

### Add Puppet-master hostname
`apt update; apt -y install vim wget`

`vi etc/hosts`

`172.17.0.1      mosaic-vm puppet-master`

## Puppet agent
### Install
`rpm -Uvh https://yum.puppet.com/puppet6-release-el-7.noarch.rpm`

`yum install -y puppet-agent`

`wget https://apt.puppetlabs.com/puppet6-release-bionic.deb`

`dpkg -i puppet6-release-bionic.deb`

`apt update; apt install -y puppet-agent`


### Config agent
`vim /etc/puppetlabs/puppet/puppet.conf`

```
[main]
certname = server1
server = mosaic-vm
```


### Test the agent
`/opt/puppetlabs/bin/puppet agent --test`


### Sign certificate on Puppet-master

 `sudo puppetserver ca sign --all`
 
