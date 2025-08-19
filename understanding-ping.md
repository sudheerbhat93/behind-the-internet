# # Understanding the Ping Command

## Objective: 
In this document, I’ve shared my learning and understanding of the Ping command, including the possible responses, their meanings, and the different request syntaxes I have learned.

---

## What is ping?
- Ping, Packet Internet Groper, is a network utility used to test the reachability of a host (computer, server, or website) on an IP network. It works by sending ICMP (Internet Control Message Protocol) Echo Request packets to the target host and waits for Echo Reply packets.

Ping helps to:
    - Check if a host is reachable.
    - Measure the round-trip time for messages sent to the host.
    - Diagnose network issues, such as packet loss or high latency.

Think of ping like shouting “Hello!” to a friend across the street:
    - If your friend shouts back, you know they heard you (host is reachable).
    - The time it takes for them to reply tells you how far away they are (network latency).
    - If they don’t reply, either they didn’t hear you, or something is blocking the message (network issue or host unreachable).

---
## Ping Syntax 

To ping any website or server 
```
ping <Domain_name or IP_Address>

```

- You can use either the domain name (like google.com) or the IP address (like 8.8.8.8) directly.

---
## Types of responses: 

### Response 1: Success

- In command prompt request `ping google.com`
- Response will be 
```
Pinging google.com [142.251.222.78] with 32 bytes of data:
Reply from 142.251.222.78: bytes=32 time=94ms TTL=118
Reply from 142.251.222.78: bytes=32 time=29ms TTL=118
Reply from 142.251.222.78: bytes=32 time=123ms TTL=118
Reply from 142.251.222.78: bytes=32 time=28ms TTL=118

Ping statistics for 142.251.222.78:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 28ms, Maximum = 123ms, Average = 68ms

```

- This means 4 request packets of 32 bytes were sent and received successfully in the time interval of the average given
- Time is the total time taken for the packet to transmit from system to system.

---

### Response 2: Request timed out

- In command prompt request `ping 192.168.1.1`
- This is a private IP of the network. 
- Response will be 
```
Pinging 192.168.1.1 with 32 bytes of data:
Request timed out.
Request timed out.
Request timed out.
Request timed out.

Ping statistics for 192.168.1.1:
    Packets: Sent = 4, Received = 0, Lost = 4 (100% loss)

```
- This means requests were sent from the system but responses not recieved. 
- This can be due to 
    - Host is offline
    - A firewall is blocking ICMP
    - The route is broken 
- In this particular case, the request is blocked as its a private IP. 

---

### Response 3: Ping transmit failed, General failure

- In command prompt request `ping 0.0.0.0`
- This IP is not a valid IP. 
- Response will be 
```
Pinging 0.0.0.0 with 32 bytes of data:
PING: transmit failed. General failure.
PING: transmit failed. General failure.
PING: transmit failed. General failure.
PING: transmit failed. General failure.

Ping statistics for 0.0.0.0:
    Packets: Sent = 4, Received = 0, Lost = 4 (100% loss)
```
- This means "I could not even send the packets" 
- The packets never left the system 
- This can be due to 
    - Invalid IP
    - No network adapter active 

---

### Response 4: Destination host unreachable 

- In command prompt request `ping 198.168.1.250`
- This is usually an unused IP 
- Response will be 

```
Pinging 192.168.0.254 with 32 bytes of data:
Reply from 192.168.0.105: Destination host unreachable.
Reply from 192.168.0.105: Destination host unreachable.
Reply from 192.168.0.105: Destination host unreachable.
Reply from 192.168.0.105: Destination host unreachable.

Ping statistics for 192.168.0.254:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
```
- This means "I sent it but I know for sure that target is unreachable"
- Packets left the system, but source was not reachable
- This can be due to 
    - No device with that IP or wrong IP
    - Routing table doesn’t know how to reach that network.
- In this case, the error is becasue there is no device with that IP
- Sometimes you also might get request timed out 

--- 

### Response 5: TTL expired in transit 

- In command prompt request `ping 8.8.8.8 -i 2`
- This is to tell the system that the request can be hopped max of 2 times. We will see this later
- Response will be 
```
Pinging 8.8.8.8 with 32 bytes of data:
Reply from 103.87.94.149: TTL expired in transit.
Reply from 103.87.94.149: TTL expired in transit.
Reply from 103.87.94.149: TTL expired in transit.
Reply from 103.87.94.149: TTL expired in transit.

Ping statistics for 8.8.8.8:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
```
- This means packets were sent but TTL dropped to zero before reaching the destination. 

#### What is TTL in ping? 
- TTL, Time to Live is a number inside every IP packet. 
- Every time the packet passes through a router (hop), the TTL value is reduced by 1.
- When TTL reaches 0, the router discards the packet and sends back: `Time to live exceeded`
- Purpose: Prevent packets from looping forever if there’s a routing error or loop
- Typical TTL values (when not modified)
    - Windows default: 128
    - Linux/macOS: 64
    - Network devices (Cisco, etc.): 255
    - This means initial value of TTL is set to this particular number in these OS
    - In our case its 128
- Example explaination: 
    - Earlier we had recieved `Reply from 142.251.222.78: bytes=32 time=58ms TTL=118` 
    - Observe `TTL=118"
    - That means the packet crossed 10 routers (128(initial value)-118(final)=10)
- You can’t know the exact starting TTL unless you know the OS/device type.
- But you can make a pretty good guess:
    - If you see a TTL around 50 → it likely started at 64 → ~14 hops.
    - If you see TTL around 118 → it likely started at 128 → ~10 hops.

---

### Response 6: Ping request could not find host

- In commain line, request `ping somewrongdomain.com`
- The response will be 
``` 
Ping request could not find host somewrongdomain.com. Please check the name and try again.
```
- This means DNS Lookup failed, windows could not even find the IP of the domain. 
- This can be due to 
    - Typo in the hostname, domain name
    - DNS server misconfigured or unreachable
    - No internet connection
    - Firwall is blocking DNS queries (port 553)

---






