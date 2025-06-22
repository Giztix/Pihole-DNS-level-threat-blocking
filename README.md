# Pihole-DNS-level-threat-blocking
Pi-hole is a lightweight network-level advertisement and tracker blocker. It is designed to run on minimal hardware such as a Raspberry Pi. Pi-hole acts as a local DNS server that intercepts and filters DNS requests before they reach external servers. 

What is DNS (Domain Name System) Resolution? 
When you type a web address like www.google.com into your browser, your device doesn’t understand domain names. It needs an IP address to connect to Google’s servers. 

That’s where DNS resolution comes into play. It’s the process of translating human-friendly domain names (e.g. www.google.com) into machine-friendly IP addresses (e.g. 142.250.70.206). 

What role do DNS Servers play? 
DNS servers are like the internet phonebooks, they respond to these translation requests.

## How DNS Resolution Works?

1. **Client Request:**
Your device asks, “What is the IP for www.google.com?”


2. **Local DNS Cache Check**
If it was recently looked up, the answer may be cached locally or on your router.


3. **Query Forwarding**
If not cached, the request is forwarded to a DNS resolver (e.g., Google DNS at 8.8.8.8, Cloudflare at 1.1.1.1, or a custom DNS like Unbound).


4. **DNS Lookup Chain**
The resolver contacts a series of authoritative servers to find the correct IP.

5. **Response Returned**
The IP address is sent back to your device, and the website loads.


Pi-hole will effectively perform these actions but it also holds a block list! This is where it has a list of domain names that it will respond with the IP address of 0.0.0.0 

This is a dead-end IP address and will load nothing. Effectively it will dead end any blocked domains and properly execute DNS resolution for every other DNS query.
