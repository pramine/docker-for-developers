# Why using Docker?

Docker has been a very commented subject lately, many articles have been written, usually talking about how to use it, auxiliary tools, integrations and the like, but many people still ask the most basic question when it’s about the possibility of using any new technology: “Why should I use this?” Or would it be: “What this has to offer me that is different from what I have today?”
![](images/docker_porque.jpg)

It is natural that people still doubt the Docker’s potential, some even think that it’s about some [hype](http://techfree.com.br/2015/06/sera-que-esse-modelo-de-containers-e-um-hype/). But in this chapter we intend to show some good reasons to use Docker. 



### 1 – Similar environments

It’s worth to highlight that Docker is not a “silver bullet” – it is not intended to solve all the problemas, much less being the only solution to several situations. Once your application is turned into a Docker imagem, it can be instantiated as a container in any environment you wish. That means you can use the application at the developer’s notebook as well as it would run at the production server.
The Docker image accepts parameters at the start of container, thus indicating that the same image can behave differently in distinct environments. This container can connect to its loca database for testing, using the credentials and the testing database. But when the container created from the image receives parameters from the production environment, it will access the database in a more robust infrastructure, with its respective production credentials and database, for instance. 

### 2 – Application as a whole package
 

Updating is also positively affected, because the [layer structure](http://techfree.com.br/2015/12/entendendo-armazenamentos-de-dados-no-docker/) of Docker allows that, in case of change, only the altered part is transferred, so the environment can be changed faster and simpler. The user only needs to execute one command to update the application image, that will be reflected on the container running on the desired moment. The Docker images can hold tags, thus making possible to store multiple versions of the same application. That means that, if there’s a problem on the update, the backup plan will be basically to use the image along with the previous tag. 


### 3 – Standardization and replication 




### 4 – Common language between infrastructure and development 




### 5 – Community 

As it is possible to access [github](http://github.com/) or [gitlab](https://about.gitlab.com/) to search code samples, using the [image repository](http://hub.docker.com/) of Docker makes possible to get good models of application infrastructure or services for complex integrations. 



### Questions

Some people sent some questions regarding the advantages we presented in this text. Thus, instead of answering them one by one, we decided to publish the questions and their answers here. 

As an example of infrastructure automation tools we have [Puppet](https://puppetlabs.com/), [Ansible](https://www.ansible.com/), and [Chef](https://www.chef.io/chef/). They can guarantee similar environments, once their job is to keep a given configuration on the desired asset. 





#### The use of the base image on Docker of a given distribution is not the same of creating a definition of a configuration management for a distribution?

No! The difference is in the host perspective. On Docker, it doesn’t matter which GNU/Linux distribution is used on the host, for there is a part of the image that carries all the files from a mini-distribution that will be sufficient to support everything the app needs. In case your Docker host is Fedora and the app needs files from Debian, don’t worry because this given image will bring up Debian files to support the environment. As said previously, this usually doesn’t affect negatively in disk space consumption.
#### Does it mean that I, as a developer, have to worry about everything on Infrastructure?

No! When we say that it is possible to the developer to specify the infrastructure, we are talking about the closest layer of the application and not all the required architecture (Basic operational system, firewall rules, network rules etc.).



#### Many people refer to Docker for be used with [microservices](https://www.thoughtworks.com/pt/insights/blog/microservices-nutshell). Is it possible to use Docker to monolithic applications?


