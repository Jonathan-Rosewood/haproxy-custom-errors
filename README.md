![preview](https://media.giphy.com/media/3ohhwfW9OgNMwDLZra/giphy.gif)

# Haproxy Custom Errors
Custom http error pages for haproxy

# Installation
Edit your `haproxy.cfg` config file
```bash
# Add this rows to "defaults" or "backend" section
errorfile 400 /etc/haproxy/errors-custom/400.http
errorfile 403 /etc/haproxy/errors-custom/403.http
errorfile 408 /etc/haproxy/errors-custom/408.http
errorfile 500 /etc/haproxy/errors-custom/500.http
errorfile 502 /etc/haproxy/errors-custom/502.http
errorfile 503 /etc/haproxy/errors-custom/503.http
errorfile 504 /etc/haproxy/errors-custom/504.http
```
