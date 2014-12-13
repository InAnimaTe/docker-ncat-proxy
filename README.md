### Ncat proxy 

This container provides the simple ability to spawn a completely transparent proxy using netcat. I would not recommend this for high performing applications as it actually runs ncat for the listen and send portions of a pass through connection.
HAProxy or NGINX should be used for more performance demanding public application.


1. Clone the repo
2. Set appropriate variables in ./run
3. Build the image
4. ????
5. Profit

> Note that you need to properly have docker or yourself modify the nat iptables rules and do similar to a `docker run -d -p 443:443 ncat-proxy` to ensure this listens properly.

##### Extra notes

I decided to not run netcat as root. To do this, I have to setcap the binary so that a non-root user can listen on a port `<1024`. Just an fyi.

