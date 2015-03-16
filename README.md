GitBucket Docker Conatiner
==========================

This is a [Docker](http://docker.io) container for [GitBucket](https://github.com/takezoe/gitbucket), a GitHub clone written in Scala. This Docker image is pretty simple as it does only 2 things:

-	Installs Java
-	Installs GitBucket

The Docker image sets up the `GITBUCKET_HOME` variable to the Docker `VOLUME` named `/var/gitbucket`. The intent is map this volume to a directory on the host. For example, if you are running in AWS, this value could be mapped to an EBS volume mouted on `/git` and we map this when we run the container from our Cloud Formation Template like so:

```
/usr/bin/docker run -d -p 8080:8080 -v /git:/var/gitbucket -m 1G damnhandy/gitbucket
```
