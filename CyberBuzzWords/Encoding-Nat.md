## Encoding, Encryption, Hashing:
- Encoding: `Convert data from one format to another, For transmission/Storage, Reversible. eg. URL encoding, Base64 encoding.`
- Encryption: `Plain text to Cipher text, For Securing transmission/Storage data, Reversible. eg. AES, RSA, SSL/TLS Encryption`
- Hashing: `Convert Input data of any size into a Fixed-size string, For data integrity and verification, Non-Reversible. eg. MD5, SHA-1, SHA-256 for Password storage & file integrity check`

## Traceroute: 
- `Used to trace the route that a data packet takes from a source to destination`

## NAT:
- Map s the Private IP to Public IPs & vice versa.
- The router uses NAT to translate the private IP addresses of the devices (e.g., 192.168.1.2, 192.168.1.3) to the router’s public IP address when accessing the internet.
```
+-------------------+       +---------------------+       +---------------+
| Private Network   |       |       Router        |       | Public Network|
|                   |       |                     |       | (The Internet)|
| +--------------+  |       | +----------------+  |       |               |
| | 192.168.1.2  |------->  | | Public IP:     |  |------>|               |
| | (Device 1)   |  |       | | 203.0.113.5    |  |       |               |
| +--------------+  |       | |----------------|  |       |               |
| +--------------+  |       | | Private IP:    |  |       |               |
| | 192.168.1.3  |------->  | | 192.168.1.1    |  |       |               |
| | (Device 2)   |  |       | +----------------+  |       |               |
| +--------------+  |       +---------------------+       +---------------+
+-------------------+
```

## VPN: 
- `Allow a secure & encrypted connection to access the internet or private network through a remote user.`



