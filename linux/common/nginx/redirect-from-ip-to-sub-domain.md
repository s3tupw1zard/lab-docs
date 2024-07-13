To prevent access to a resource only using the public IP address, we can add the following to our server block where we listen on 443. I added it below the server_name directive:

```nginx
    if ( $host != "example.com" ) {
        return 301 https://$server_name$request_uri;
    }
```

Replace example.com with your domain or subdomain.

The config should look like this:

```nginx
...

server {
    listen 443 ssl http2;
    server_name example.com;

    if ( $host != "example.com" ) {
        return 301 https://$server_name$request_uri;
    }
    
    root /var/www/htlm;
    index index.php;

...

}
```
