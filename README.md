# DOCKER PORTAINER

![/images/1.jpg](/images/2)

Portainer is a lightweight management UI which allows you to easily manage your Docker host or Swarm cluster.

## Index

1. [What's Docker Portainer?](#whatsportainer)
2. [How to install Docker Portainer](#install)
3. [How to access Docker Portainer](#access)
4. [Portainer's control panel](#control)
5. [Let's deploy a sample container](#sample)
6. [Conclusion](#conclusion)
7. [References](#references)

<a name="whatsportainer"></a>
## 1. What's Portainer?
Portainer is meant to be as simple to deploy as it is to use. It consists of a single container that can run on any Docker engine (Docker for Linux and Docker for Windows are supported). Portainer allows you to manage your Docker stacks, containers, images, volumes, networks and more! It is compatible with the standalone Docker engine and with Docker Swarm.

Portainer is built to run on Docker and is really simple to deploy. Portainer deployment scenarios can be executed on any platform unless specified.

Warning: Portainer supports the Current Docker version and two prior versions ONLY. Older versions may run, but are not supported in any way.

<a name="install"></a>
## How to install Portainer

Portainer is comprised of two elements, the Portainer Server, and the Portainer Agent. Both elements run as lightweight Docker containers on a Docker engine or within a Swarm cluster.

The first thing we have to do is deploy a Portainer server. So let's start creating it's volume which will contain all container's data:

```
$ docker volume create portainer_data
```

Now let's create the container. The image is portainer/portainer-ce, the port needed are 8000:8000 and 9000:9000. Don't forget to run it on background so we can continue using linux's terminal:

```
$ docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
```

Once docker finishes we will have our Portainer container ready to use, we just have to access it!

<a name="access"></a>
## How to access Docker Portainer

Now that we have our portainer server ready, we will access it though the port 9000, just as you can see in the image below:

![/images/3](/images/3)

Once we are in we will be able to create our admin account:

![/images/4](/images/4)

Now let's select which environment we want to maange, in this case we will choose Docker:

![/images/5](/images/5)

Well done! Here we'll be able to easily work with Docker using Portainer. In the left list we can select what we can manage: images, volumes, networks, containers, etc. In the next section we'll explore each tab a little bit more:

![/images/6](/images/6)

<a name="control"></a>
## Portainer's Control Panel

In this section we're going to explore the most useful portainer's tab. To begin, we just have to select one element from the list to the left:

![/images/7](/images/7)

1.- Dashboad

![/images/8](/images/8)

Here we have a Docker's objects summary. We can easily see how many stacks, volumes, images, containers and network we have.

2.- App Templates

![/images/9](/images/9)

In this tab we have the aplication templates list where we can quickly deploy containers using images from here. We have databases, CMS backups, etc. We also have the option to create our own templates! If the select one we'll see that we just have to select its name and network and then our new container'll be ready to be created:

![/images/9.1.png](/images/9.1.png)

3.- Containers

![/images/10](/images/10)

This tab contains a list with all our containers, we can see their status, some quick actions we can perfom (see their logs, or read more about them), their stack, the image they were created with, when they were created, their open ports and their user. 

4.- Images

![/images/11](/images/11)

As you can see, in the images tab there's a list with all our images. We also have the option to pull images, we just have to write their registry and name!

5.- Networks



6.- Volumes


<a name="sample"></a>
## Let's deploy a sample container
### Our container structure:
- Image: httpd
- Port: 8082



### Customizing our webpage

<a name="conclusion"></a>
## Conclusion

<a name="references"></a>
## References
- [Portainer's Official Webpage](https://www.portainer.io/)
- [Github Official Portainer Repository](https://github.com/portainer/portainer)
