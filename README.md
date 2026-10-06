# Site-to-Site-IPsec-VPN-Implementation-Cisco-Packet-Tracer-
A basic implementation of a secure Site-to-Site IPsec VPN tunnel connecting two remote LAN subnets across an untrusted WAN network using Cisco ISR 4331 routers.


<img width="1900" height="980" alt="Screenshot 2026-09-23 180959" src="https://github.com/user-attachments/assets/690211c2-87c4-4673-813c-59c32e39f8ba" />


Assign IPs: Set LAN and WAN IP addresses on R1, R2, PC1, and PC2.   

Add Default Routes: Point R1 WAN traffic to R2 (203.0.113.2) and R2 to R1 (203.0.113.1).

Define Interesting Traffic: Create ACL 100 on both routers to match local LAN to remote LAN traffic.   

Set Up Phase 1 (IKE): Configure ISAKMP policy (AES, SHA, pre-shared key) and set the peer IP/key on both routers.   

Set Up Phase 2 (IPsec): Define the transform set (esp-aes esp-sha-hmac) for data encryption.   

Bind & Apply Crypto Map: Link the ACL, transform set, and peer IP into a crypto map, then attach it to WAN interface Gig0/0/1 on both routers.   

Test & Verify: Ping PC2 (192.168.20.10) from PC1 and run show crypto ipsec sa on R1 to confirm encrypted packets (#pkts encrypt). 
