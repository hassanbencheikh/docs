# Local configuration

* primary DNS server

```bash
sudo nano /etc/resolv.conf

#nameserver 127.0.0.1
nameserver $ip
```

* ip addresses to hostnames

```bash
sudo nxc smb $ip --generate-hosts-file /etc/hosts
```

* kerberos configuration

```bash
nxc smb $dc -u $user -p $pass --generate-krb5-file krb5.conf
cat krb5.conf | sudo tee /etc/krb5.conf
```

* time difference (fix)

```bash
sudo timedatectl set-ntp off
sudo rdate -n $ip
```

* shell stabilization

```bash
python3 -c 'import pty;pty.spawn("/bin/bash")'
export TERM=xterm
CTRL+Z
stty raw -echo;fg
```
