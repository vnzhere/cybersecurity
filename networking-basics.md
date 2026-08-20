
<!-- #1. checks your machine network info -->
<!--  lists your network interface and their ip addresses  -->
#1.ip addr show



<!-- checks if remote host is reachable -->
<!-- sends small packages to google.com and checks the connectivity, waits for reply -->
<!-- ctrl+c to stop it -->
#2. ping google.com



<!--  DNS lookup; converts domain name into ip address.-->
#3. nslookup google.com



#4. traceroute google.com
<!--  Traces network path for the domain name.-->



#5. Netstat -tuln
<!--  Gives local, ipv4 and 6 ports along with tcp and udp types.-->
<!-- Listen state– means waiting for connection -->



<!-- make a network request and show what server sends back -->
<!-- Use curl to communicate with a server directly from terminal without opening a browser -->
#6. curl -I https://example.com
<!-- -I gives headers only
Content type is html
Cloudflare introduced 
http/200 means successful responses
cf-cache-status:HIT means response served from cloudfare cache. 
 -->