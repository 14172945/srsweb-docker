# srsweb-docker
SRS (Simple Realtime Server) is deployed in docker and supports FLV streaming on the page.

## How to use

First, obtain the latest SRS image
```
docker pull ossrs/srs:v6
```

Then run it inside the docker container
```
docker run -p 1935:1935 -p 1985:1985 -p 8080:8080 --name srs -d ossrs/srs:v6
```

* Among them, port 1935 is the RTMP service port, 1985 is the console port, and 8080 is the default port.

Visit: [http://HostIP:8080/](http://HostIP:8080/)

Click [http://HostIP:1985/console/](http://HostIP::1985/console/)You can see the usage of the server and clients, the load of the server, etc.

## Set up

* Click the Settings option in the OBS software and select the push settings

Select Custom as the service mode, [rtmp://HostIP/live/live server](rtmp://HostIP/live/live server), and stream key: [stream](stream)

* Then click the Start Streaming button to push the stream

On the [SRS console page](http://HostIP:1985/console/), you will see that the server has received the RTMP stream.

## How to play

* 1.Use the preview of the SRS console page to play it.

* 2.Play with a custom HTML page.

Pull the source code of this repository.

```
git@github.com:14172945/srsweb-docker.git
```

Modify the HTTP address on line 15 in inedx.

For example:[http://HostIP:8080/live/live/stream.flv](http://HostIP:8080/live/live/stream.flv)

Upload the index file to your web server, and you can deploy it using Nginx and others.

Finally, visit your address to view it.
