`import ipaddress`

### define an IP address and network address
```
ip_string = '192.168.0.1'
ip_address = ipaddress.ip_address(ip_string)
```

```
network_string = '192.168.0.0/28'
network_address = ipaddress.ip_network(network_string)
```

To validate an IP address
```


try:
    ip = ipaddress.ip_address(ip_string)
    print('%s is a correct IP%s address.' % (ip, ip.version))
except ValueError:
    print('address/netmask is invalid: %s' % ip_string)
```

### print network mask in dot format
```
network = ipaddress.IPv4Network('192.168.0.0/29')
print(network.netmask)
255.255.255.248
```

### create a network and list its hosts
```
network = ipaddress.IPv4Network('192.168.0.0/29')
hosts = network.hosts()
print(list(hosts))
[IPv4Address('192.168.0.1'), IPv4Address('192.168.0.2'), IPv4Address('192.168.0.3'), IPv4Address('192.168.0.4'), IPv4Address('192.168.0.5'), IPv4Address('192.168.0.6')]
```

Note that the returned hosts are not strings, they are of type IPAddress. To turn this list to a list of strings
```
host_list = []
for host in hosts:
  host_list.append(format(host))
print(host_list)
['192.168.0.1', '192.168.0.2', '192.168.0.3', '192.168.0.4', '192.168.0.5', '192.168.0.6']
```

### devide a supernet to subnets
```
network = ipaddress.IPv4Network('192.168.0.0/16')
network_18_subnets = network.subnets(new_prefix=18)
print(list(network_18_subnets))
[IPv4Network('192.168.0.0/18'), IPv4Network('192.168.64.0/18'), IPv4Network('192.168.128.0/18'), IPv4Network('192.168.192.0/18')]
```

To turn the list of IPv4Network to a list of strings
```
subnets = []
for subnet in network_18_subnets:
  subnets.append(format(subnet))
print(subnets)
['192.168.0.0/18', '192.168.64.0/18', '192.168.128.0/18', '192.168.192.0/18']
```

### pop an item from a list
```
prefix = subnets.pop(0)
print(prefix)
'192.168.0.0/18'
print(subnets)
['192.168.64.0/18', '192.168.128.0/18', '192.168.192.0/18']
```
Note that pop() will remove the latest item