
# Docker installation choices
If you’re running Linux, it’s quite simple. You can just use your distro’s package manager to install Docker Engine and you’re good to go. Then you’re free to install other supporting tools later.

Both OSX and Windows users aren’t so lucky, but as time goes on, getting Docker to run on all major platforms is getting better and better. As of this post, there are 2 ways, both with their pros and cons.

## [Docker Toolbox](https://www.docker.com/products/docker-toolbox)

The first method we’ll look at is called the Docker Toolbox. It is appropriately named because it’s an installation tool that pulls together a few different tools, mainly the Docker Machine, that lets you create the Virtual Box driven VM that runs Docker

The tools are:

* Docker Engine - Service that runs which allows you to create Docker images and run Docker containers
* Docker Compose - Lets you 'compose' docker commands, so you can run more than one Docker containers at a time
* Docker Machine - Used to create the Virtual Box driven VM that runs Docker
* Virtual Box - Gives your system a hypervisor required by Docker that was not originally there
* Pre-configured shell to interact with Docker - The quickstart terminal
* Kitematic -  A 'nice to have' Graphical tool that lets you manage your Docker images and containers

The bottom 3 tools are specific to the Docker Toolbox.


## [Docker for Mac / Docker for Windows](https://docs.docker.com/)

Docker for Mac / Docker for Windows lets you run Docker through OSX’ and Windows’ native hypervisors. On OSX that would be HyperKit and on Windows that’s Hyper-V.

Instead of having to lug around a clunky Virtual Box driven VM, you can just let your OS’ native hypervisor deal with things. In theory this will use less resources and be much faster.

Docker for Mac / Windows installs the following tools:

Docker Engine
Docker Compose
Docker Machine


### Docker Toolbox vs. Docker for Mac / Windows?

If you are wondering as to what your computer needs to run either installation method, here are some points.

#### Requirements for Docker Toolbox

You must not be running HyperKit or Hyper-V.

If you are, then you cannot use the Docker Toolbox because you cannot have Virtual Box running together with HyperKit or Hyper-V. There are hacks you can do to modify your system’s boot flags to switch between using both but that’s likely not worth the hassle.

You must be running OSX Mountain Lion 10.8 or newer. If you’re on Windows you must be running Windows 7 or newer. Read the full requirements for [OSX](https://docs.docker.com/toolbox/toolbox_install_mac/?utm_source=nickjanetakis.com&utm_medium=blogpost) and [Windows](https://docs.docker.com/toolbox/toolbox_install_windows/?utm_source=nickjanetakis.com&utm_medium=blogpost) on Docker’s site.

#### OSX requirements for Docker for Mac

To run HyperKit you need OSX Yosemite 10.10.3 or later with a Mac from 2010 or later due to its hardware requirements of memory management unit (MMU) virtualization, Extended Page Tables (EPT) and Unrestricted Mode.

It’s also worth noting that moving forward, Docker is only going to officially support El Capitan 10.11 and newer versions of OSX.

These stats are listed on Docker’s official [Docker for Mac documentation](https://docs.docker.com/docker-for-mac/?utm_source=nickjanetakis.com&utm_medium=blogpost).

#### Windows requirements for Docker for Windows

To run Hyper-V you need Windows 10 Professional, Education or Enterprise. Virtualization also needs to be enabled (it probably is). These stats are listed on Docker’s official Docker for Windows documentation.

### Usability concerns

With the Docker Toolbox approach, your Docker host (the machine running Docker Engine) is ran through a VM which in turn is a computer on your local network.

This means when you read certain guides online, you may see people reference localhost. For example, if you Dockerized a web application and the guide told you to goto ` localhost:8000 ` you would not be able to access that if you used the Docker Toolbox approach.

Instead you would have to goto your Docker Machine’s IP address which is likely going to be ` 192.168.99.100:8000 `.

If you used Docker for Mac / Windows you would be able to access localhost:8000 because your Docker host is running locally.

### Performance concerns

Docker has this concept of mounting files and folders from your OS into a running container. That might not make sense to you now but it will when you start feeling the pain of your web server taking 9 seconds to reload when it should only take 1.

With Linux, it’s super fast and you can’t even notice you’re running your code inside of a Docker container but on OSX and Windows there are some performance issues.

Keep in mind, these issues are typically only in development mode where you want to mount in your source code so you can get real time feedback without having to re-build your Docker images.

Anyways, the Docker Toolbox approach seems to be a bit more polished when it comes to performance as per feedbacks.

So which one should you pick?

I recommend going with the Docker for Mac / Windows method if your system is capable of running it. Then I would keep using it until (or if!) you run into performance related issues.

If you run into show stopping performance issues then go with the Docker Toolbox approach.

If you’re on Windows and you’re serious about Linux development you may also want to run your Linux development environment in a graphical seamless virtual machine. It gives you the best of both worlds because you can run Docker on Linux natively.




### References
* [Docker](https://docs.docker.com/)
* [Anaconda and docker](https://www.continuum.io/blog/developer-blog/anaconda-and-docker-better-together-reproducible-data-science)
* [Docker data science](https://www.dataquest.io/blog/docker-data-science/)
* [Docker blog for beginners](https://nickjanetakis.com/blog/docker-toolbox-docker-machine-docker-compose-docker-wtf)


