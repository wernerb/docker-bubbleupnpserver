# docker-bubbleupnpserver

For use with the [BubbleUPnP app](https://play.google.com/store/apps/details?id=com.bubblesoft.android.bubbleupnp) for android. This allows automatic transcoding for specific targets, namely the Google Chromecast. 

The Chromecast does not support ac3 or dts audio streams and so needs to be transcoded. The BubbleUPnP app in conjunction with this server will allow the chromecast to play a wide selection of media formats.

### Prerequisites
* Install docker 
* Set up a bridge. Your docker container must run on an IP that reaches your media players. See the [Setting up a network bridge section on this blog](http://blog.ostanin.org/2013/09/14/plex-media-server-in-docker/)


### Quick start
Pull from docker and start:

    $ docker run -d --networking=false \
      --lxc-conf="lxc.network.type = veth" \
      --lxc-conf="lxc.network.flags = up" \
      --lxc-conf="lxc.network.link = br0" \
      --lxc-conf="lxc.network.ipv4 = 192.168.1.48" \
      --lxc-conf="lxc.network.ipv4.gateway=192.168.1.1" \
      wernerb/bubbleupnpserver

Ps. Replace `br0`, `192.168.1.48` and `192.168.1.1` with the bridge interface, desired ip for container and your network gateway IP.

### Build manually
To build and run yourself. Clone this repository and from that folder run:

    $ docker build -t wernerb/bubbleupnpserver . 
    
Then use the Quick start command to run the bubbleupnpserver.


### Trusted build
This container is also available as a Trusted Build on the [docker index](https://index.docker.io/u/wernerb/bubbleupnpserver/)
