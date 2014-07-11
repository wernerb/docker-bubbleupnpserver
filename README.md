# docker-bubbleupnpserver

For use with the [BubbleUPnP app](https://play.google.com/store/apps/details?id=com.bubblesoft.android.bubbleupnp) for android. This allows automatic transcoding for specific targets, namely the Google Chromecast. 

The Chromecast does not support ac3 or dts audio streams and so needs to be transcoded. The BubbleUPnP app in conjunction with this server will allow the chromecast to play a wide selection of media formats.

### Prerequisites
* Install docker 

### Quick start
Pull from docker and start:

    $ docker run -d --net=host --privileged wernerb/bubbleupnpserver

### Build manually
To build and run yourself. Clone this repository and from that folder run:

    $ docker build -t wernerb/bubbleupnpserver . 
    
Then use the Quick start command to run the bubbleupnpserver.

### Trusted build
This container is also available as a Trusted Build on the [docker index](https://index.docker.io/u/wernerb/bubbleupnpserver/)
