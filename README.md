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

<a name="control"></a>
## Portainer's Control Panel

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
