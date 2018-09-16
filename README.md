# Craft Vagrant

This is a vagrant for Craft CMS projects

## Installation

Firstly, ensure you have Vagrant installed, then:

```
git clone https://github.com/martynbiz/craft-vagrant myproject
cd myproject
cp Vagrantfile.example Vagrantfile
cp provision.sh.example provision.sh
```

Add the blog.vagrant domain to the /etc/hosts file:

```
192.168.33.120	craft.vagrant
```

This domain can be changed if preferred. See optional changes below.

## Optional changes

Make whatever changes you need to VagrantFile and provision.sh (or leave as is for
default configuration). Below are some recommended/optional changes:

### Change network IP and/or domain

The are a couple changes required:

VagrantFile

```
config.vm.network "private_network", ip: "<new IP address>"
```

This new IP address must match the IP address in /etc/hosts.

Also, if changing the domain, find instances of blog.vagrant in provision.sh file
and change those to the new domain if that has changed too.

## Run vagrant

Now that provision.sh and Vagrantfile are ready, start up the vagrant instance:

```
vagrant up
```

It should now be possible to view the new blog in the browser with the domain used.
This will be http://craft.vagrant if unchanged.
