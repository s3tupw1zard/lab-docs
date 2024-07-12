In the lab repository I added my own docker daemon.json with changes to make docker use IPv6 addresses.

The content is as follows:

```json
{
"ipv6": true,
"fixed-cidr-v6": "2001:db8:1::/64",
"experimental": true,
"ip6tables": true
}
```

This ensures that internally Docker uses a IPv6 for external connectivity over IPv6. This is useful for IPv6-only servers.