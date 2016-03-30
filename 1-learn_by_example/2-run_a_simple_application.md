# [Run a Simple Application](https://docs.docker.com/engine/userguide/containers/usingdocker/) #

----------

## Running a web application in Docker ##

```shell
$ docker run -d -P training/webapp python app.py
```

* `-P` and tells Docker to map any required network ports inside our container to our host, it can be switched to `-p <localport>:5000` to specify localport
* **training/webapp**: This image is a pre-built image you’ve created that contains a simple Python Flask web application

Using the below 2 commands to find the virtual localhost IP and port:

```shell
$ docker-machine ip [your-vm-name]
```

```shell
$ docker port [container name] [container port]
```

And then go to `[IP]:[port]` to see the result.






