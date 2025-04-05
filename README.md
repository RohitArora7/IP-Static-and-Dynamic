# IP-Static-and-Dynamic


at VM install
```
sudo apt update
sudo apt install openssh-server
```
get ip of vm
```
ip -a
```
take ssh
```
ssh ubuntu@192.168.122.2
ssh-copy-id ubuntu@192.168.122.2
```
cd /etc/netplan

Dynamic 
```yaml
network:
  ethernets:
    enp1s0:
      dhcp4: true
  version: 2
```

Static
```yaml
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

new static
```
network:
  version: 2
  ethernets:
    enp1s0:
      addresses:
        - 192.168.122.245/24
      routes:
        - to: default
          via: 192.168.122.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4
```


```bash
sudo netplan apply 
```
```bash
sudo systemctl restart NetworkManager 
```
