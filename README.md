# vagrant-azure-ubuntu

A vagrant box for ASP.NET VNEXT & mono running on the vagrant-azure provider

## Installation
First, make sure that you have [Vagrant](http://www.vagrantup.com/downloads) and 
the Vagrant [Azure provider](https://github.com/MSOpenTech/vagrant-azure) properly installed.

To install vagrant-azure:

```
$ vagrant plugin install vagrant-azure
```

1. Run `vagrant up --provider=azure`
2. Run `vagrant ssh`
3. Run `kpm restore`
4. Navigate to `/helloworld/src/helloworldweb`
5. Type `k web`
6. Open a browser and type `http://<azurecloudservice>.cloudapp.net`
7. When you're finished, type `vagrant destroy`