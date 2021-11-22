# IP-Static-and-Dynamic

Dynamic 
```bash
network:
  ethernets:
    enp1s0:
      dhcp4: true
  version: 2
```

Static
```bash
network:
 ethernets:
  enp1s0:
    addresses:
     - 192.168.122.245/24
    gateway4: 192.168.122.1
    nameservers:
      addresses:
      - 8.8.8.8
      - 8.8.4.4
      search: []
 version: 2
```

