Here I replaced the following:

```json
{
    "server.properties": {
        "parser": "properties",
        "find": {
            "server-ip": "0.0.0.0",
            "server-port": "{{server.allocations.default.port}}",
            "query.port": "{{server.allocations.default.port}}"
        }
    }
}
```

with the following:

```json
{
    "server.properties": {
        "parser": "properties",
        "find": {
            "server-ip": "::",
            "server-port": "{{server.allocations.default.port}}",
            "query.port": "{{server.allocations.default.port}}"
        }
    }
}
```

This ensures that the server inside the container is bound to a IPv6 address.