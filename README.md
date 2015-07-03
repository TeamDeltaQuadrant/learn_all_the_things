![](https://torsaporsa.files.wordpress.com/2013/09/iltni.jpg)

## Contents:
- [Docker vs Vagrant](#docker-vs-vagrant)
- [Puppet vs Chef](#puppet-vs-chef)
- [Testing](#testing)
  - [RSpec vs Cucumber](#rspec-vs-cucumber)


##Docker vs Vagrant

####Vagrent

Vagrant provides easy to configure, reproducible, and portable work environments built on top of industry-standard technology and controlled by a single consistent workflow to help maximize the productivity and flexibility of you and your team.
To achieve its magic, Vagrant stands on the shoulders of giants. Machines are provisioned on top of VirtualBox, VMware, AWS, or any other provider. Then, industry-standard provisioning tools such as shell scripts, Chef, or Puppet, can be used to automatically install and configure software on the machine.

**In simple words**, Vagrant is a technology which takes a file ( Vagrantfile ) to install an operating system ( could be anyone, normally is the OS that you will use in your servers or cloud instances ) and install all the libraries and software you need to run the programs and processes that form part of your final application. In other words, Vagrant could install your OS and then your Docker packages to run your Docker containers in your computer and in your server.

All this allows you to create similar environments ( no exactly the same but really close to each other ) where you can test your applications.

**So, in summary:**

>Vagrant is a technology that will allow you to install all you need to develop your application in an easy and simple way.

####Docker

Docker is an open-source project to easily create lightweight, portable, self-sufficient containers from any application. The same container that a developer builds and tests on a laptop can run at scale, in production, on VMs, bare metal, OpenStack clusters, public clouds and more.

**Again in simple words**, Docker is a technology that allows you to run applications inside containers ( that resemble virtual machines but are really different ) which assure you that all the libraries and packages needed by an specific application are always available and are always the same without mattering where you run them. That means that you can make a container for Memcache and another for Redis and you can be sure that in any Linux OS where you run your containers ( including the operating system that Vagrant just installed in your computer or server ), they will have the same behavior.

**So, in summary:**

>Docker is a technology that allows you to run self-contained applications eliminating worries about dependencies and libraries.

#### Interesting Quora Awnsers:
**Short answer: Vagrant abstracts the machine where as Docker abstracts the application..**

**Vagrant** uses virtualbox to spin up a virtual machine for you where you can set up your own environment and install everything you need on that machine mostly through some provisioning scripts. Its most common use case is to test your application on different environments and spin up test servers/machines where your teammates can ssh to and test their work on where everyone else can see and use.

**Docker** on the other hand uses images and containers to build your application as an image. An image is basically an instance of your application with all of its setup environment and requirements installed, however its not a machine.. A container is basically a process/service that runs on the background, it acts as a virtual machine that contains your images, but its not one, its just a service that runs on top of a machine. You can run many images in one container and you can run many containers on one machine.

If you have your docker image, you can run your application on any machine, all you need is to have docker installed. Docker uses dockerhub as a CDN where users can pull/push images from repositories.
[Source](http://www.quora.com/What-is-the-difference-between-Docker-and-Vagrant-When-should-you-use-each-one)


**The author of Vagrant says:**

>It isn't correct to directly compare Vagrant to Docker. In some scenarios, they do overlap, and in the vast majority, they don't. Actually, the more apt comparison would be Vagrant versus something like Boot2Docker (minimal OS that can run Docker). Vagrant is a level above Docker in terms of abstractions, so it isn't a fair comparison in most cases.

>Vagrant launches things to run apps/services for the purpose of development. This can be on VirtualBox, VMware. It can be remote like AWS, OpenStack. Within those, if you use containers, Vagrant doesn't care, and embraces that: it can automatically install, pull down, build, and run Docker containers, for example. With Vagrant 1.6, Vagrant has docker-based development environments, and supports using Docker with the same workflow as Vagrant across Linux, Mac, and Windows. Vagrant doesn't try to replace Docker here, it embraces Docker practices.

>Docker specifically runs Docker containers. If you're comparing directly to Vagrant: it is specifically a more specific (can only run Docker containers), less flexible (requires Linux or Linux host somewhere) solution. Of course if you're talking about production or CI, there is no comparison to Vagrant! Vagrant doesn't live in these environments, and so Docker should be used.


>**In conclusion:** in highly specific use cases, Docker is certainly a possible replacement for Vagrant. In most use cases, it is not. Vagrant doesn't hinder your usage of Docker; it actually does what it can to make that experience smoother. If you find this isn't true, I'm happy to take suggestions to improve things, since a goal of Vagrant is to work equally well with any system.



**the author of Docker says:**


>The short answer is that if you want to manage machines, you should use Vagrant. And if you want to build and run applications environments, you should use Docker.

>Vagrant is a tool for managing virtual machines. Docker is a tool for building and deploying applications by packaging them into lightweight containers. A container can hold pretty much any software component along with its dependencies (executables, libraries, configuration files etc.), and execute it in a guaranteed and repeatable runtime environment. This makes it very easy to build your app once and deploy it anywhere - on your laptop for testing, then on different servers for live deployment etc.

>**In summary:** Vagrant is for managing machines, Docker is for building and running application environments.

[Source](http://stackoverflow.com/questions/16647069/should-i-use-vagrant-or-docker-io-for-creating-an-isolated-environment)



##Puppet vs Chef


##Testing
###RSpec vs Cucumber
