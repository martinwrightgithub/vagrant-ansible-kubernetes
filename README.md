# vagrant-ansible-kubernetes

Introduction 

This is demo of a basic deployment helloworld app on kubernetes. 

To start type

`vagrant up` 

## Known problems. 

The ansible task “start minikube” sometimes fails the first time you run it. To resolve this vagrant ssh in to the vagrant box run and run “minikube start”

The helloworld kubernetes service can’t find port 80. Ideally I would like helloworld viewable form outside the VM on 192.168.33.22
However it is view from inside vagrant curl http://192.168.49.2:32080 

# Improvements.

### Kubernetes 

I shouldn’t have used minikube. This is a quick and easy tool to get started on kubernetes on your local computer. I thought this might save me time, as I’m a beginner to kubernetes. However this caused all sorts of issues, like the one I have when I ansible for this first time. 
This is the approach I should have taken with two VM a master and a node.
https://kubernetes.io/blog/2019/03/15/kubernetes-setup-using-ansible-and-vagrant/

### Docker

I used a folk of a nginx hello world container in order to save fime. I would like to maybe do it again using my own. 

https://github.com/martinwrightgithub/docker-helloworld


### Ansible

I should consider create a full ansible project, rather then a single playbook file. This would allow it broken in to different roles and hosts, would make it easier to manage when the applications grows to include to new features.

I should maybe consider downloading minikube to a /tmp to directory rather then vagrants home directory, to keep the home directory tidy. 

I should maybe double check to make sure I’m using the correct permission for files and directory. 
