### Ncat proxy 

This container provides the simple ability to spawn a completely transparent proxy using netcat. I would not recommend this for high performing applications as it actually runs ncat for the listen and send portions of a pass through connection.
HAProxy or NGINX should be used for more performance demanding public application.


1. Clone the repo
2. Build the image
3. ????
4. Profit


To properly run this, do someething like `docker run -d -p 1234:1234 -e DEST_HOST="example.com" -e DEST_PORT=443 -e LOCAL_PORT=1234 -e MAX_CONN=4028 --name ncat-proxy inanimate/ncat-proxy`

##### Extra notes

I decided to not run netcat as root. To do this, I have to setcap the binary so that a non-root user can listen on a port `<1024`. Just an fyi.

