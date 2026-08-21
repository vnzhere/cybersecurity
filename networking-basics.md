git add . && git commit -m "Add networking and tcpdump basics" && git push
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
http/2---200 means successful responses
cf-cache-status:HIT means response served from cloudfare cache. 
 -->


 <!-- read real packets of tcpdump -->

 #1. ipconfig or  ip link show
 <!-- 1. show all network of your device
 2. en0--- wifi interface
 lo0--- lookback ie device talking to itself -->

 #2. capture 10 packets: sudo tcpdump -i en0 -c 10
 <!-- 1. tcpdump--- watches network package going through your device
 2. -i en0--- listens to wifi traffic
 3. -c 10 ---- stop after 10 packets -->


 #3. capture traffic from google: sudo tcpdump -i en0 -c 10 host google.com -v
 <!-- 1. shows packets to/from google
 2. host google.com--- filter google traffic
 3. -v--- shows extra packet info -->

#4. watch tcp connection packets: sudo tcpdump -i en0'tcp[tcpflags]&(tcp-syn/tcp-ack)!=0' -c 6

<!-- 1. shows tcp SYN/ACK packets used while establishing connections -->

#5. save packets for later: sudo tcpdump -i en0 -c 20 -w capture.pcap
<!-- 1. captures 20 packets 
2. instead of displaying--- it saves them on capture.pcap
3. later on tools like wireshark, opens file for detailed analysis -->


#6. use curl https:example.com
<!-- shows tcp connection happening -->