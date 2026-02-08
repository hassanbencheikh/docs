# Port scanning

Active Directory (AD) ports are specific network communication endpoints that enable different services to interact so that the entire AD infrastructure functions correctly. These ports are used for a variety of critical tasks, such as replicating data between domain controllers and authenticating users and computers.

`53/TCP+UDP` (DNS)\
`88/TCP+UDP` (Kerberos)\
`123/UDP` (W32Time)\
`135/TCP` (RPC Endpoint Mapper)\
`137/TCP+UDP` (NetBIOS-NS)\
`138/UDP` (NetBIOS Datagram)\
`139/TCP` (NetBIOS Session)\
`389/TCP+UDP` (LDAP)\
`445/TCP` (SMB)\
`464/TCP+UDP` (Kerberos Pwd Change)\
`49152-65535/TCP+UDP` (RPC Dynamic)\
`5722/TCP` (DFS-R)\
`5985/TCP` (WinRM HTTP)\
`5986/TCP` (WinRM HTTPS)\
`636/TCP` (LDAPS)\
`3268/TCP` (Global Catalog)\
`3269/TCP` (GC SSL)\
`9389/TCP` (AD Web Services)

* open ports

```bash
nmap -p- $ip --min-rate 1000 -nv
```

* Default scripts and version

```shellscript
nmap -p53,88 $ip -sCV --min-rate 1000 -nv
```

#### Resources

[https://www.manageengine.com/products/ad-manager/blog/active-directory-firewall-ports.html](https://www.manageengine.com/products/ad-manager/blog/active-directory-firewall-ports.html)
