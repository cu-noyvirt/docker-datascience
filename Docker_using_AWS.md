

#### Docker is a technology that allows you to build, run, test, and deploy distributed applications that are based on Linux containers.

#### Running Docker on AWS provides a highly reliable, low-cost way to quickly build, run, test, and deploy distributed applications at any scale. AWS provides support for Docker open-source and commercial solutions within AWS services.

#### Amazon ECS uses Docker images in task definitions to launch containers on EC2 instances in your clusters.

#### To install Docker on an Amazon Linux instance:

- Launch an instance with the Amazon Linux AMI. For more information, see [Launching an Instance](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/launching-instance.html) in the Amazon EC2 User Guide for Linux Instances.

- Connect to your instance. For more information, see [Connect to Your Linux Instance](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstances.html) in the Amazon EC2 User Guide for Linux Instances.

- Update the installed packages and package cache on your instance.
```
[ec2-user ~]$ sudo apt-get update
```

- Install Docker.
 ```
 [ec2-user ~]$ sudo apt-get install docker
 sudo apt install docker.io
 ```

- Start the Docker service.
```
[ec2-user ~]$ sudo service docker start
```

- Verify that the ec2-user can run Docker commands.
 ```
 docker info
 ```

 
