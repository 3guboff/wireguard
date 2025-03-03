# Install and use Wireguard
Scripts automate the installation and use of Wireguard on Ubuntu Server

## How use

### Installation
```
git clone https://github.com/3guboff/wireguard.git wireguard
cd wireguard
sudo ./initial.sh
```

The `initial.sh` script removes the previous Wireguard installation (if any) using the `remove.sh` script. It then installs and configures the Wireguard service using the `install.sh` script. And then creates a client using the `add-client.sh` script.

### Add new customer
`add-client.sh` - Script to add a new VPN client. As a result of the execution, it creates a configuration file ($CLIENT_NAME.conf) on the path ./clients/$CLIENT_NAME/, displays a QR code with the configuration.

```
sudo ./add-client.sh
#OR
sudo ./add-client.sh $CLIENT_NAME
```

### Reset customers
`reset.sh` - script that removes information about clients. And stopping the VPN server Winguard
```
sudo ./reset.sh
```

### Delete Wireguard
```
sudo ./remove.sh
```

### Notes:
```
Rule for Asus RT-AC87U-1540 with forwarding to other server (192.168.100.2):
iptables -t nat -A VSERVER -i eth0 -p udp -m udp --dport 51820 -j DNAT --to-destination 192.168.100.2:51820
```

