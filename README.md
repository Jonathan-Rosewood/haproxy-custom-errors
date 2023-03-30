![preview](https://media.giphy.com/media/3ohhwfW9OgNMwDLZra/giphy.gif)

# Haproxy Custom Errors
Custom http error pages for HAProxy

# Error Code Definitions
In the [RFC 9110](https://httpwg.org/specs/rfc9110.html#status.codes) is every http status code presented with a deep and great description but for the most of us a short description is more than enough for the short version check the great work of [Mozzila.org](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

# Installation
Edit your `haproxy.cfg` config file
```bash
# Add this rows to "defaults" or "backend" section
errorfile 400 /etc/haproxy/errors-custom/400.http
errorfile 401 /etc/haproxy/errors-custom/401.http
errorfile 402 /etc/haproxy/errors-custom/402.http
errorfile 403 /etc/haproxy/errors-custom/403.http
errorfile 404 /etc/haproxy/errors-custom/404.http
errorfile 405 /etc/haproxy/errors-custom/405.http
errorfile 406 /etc/haproxy/errors-custom/406.http
errorfile 407 /etc/haproxy/errors-custom/407.http
errorfile 408 /etc/haproxy/errors-custom/408.http
errorfile 409 /etc/haproxy/errors-custom/409.http
errorfile 410 /etc/haproxy/errors-custom/410.http
errorfile 411 /etc/haproxy/errors-custom/411.http
errorfile 412 /etc/haproxy/errors-custom/412.http
errorfile 413 /etc/haproxy/errors-custom/413.http
errorfile 414 /etc/haproxy/errors-custom/414.http
errorfile 415 /etc/haproxy/errors-custom/415.http
errorfile 416 /etc/haproxy/errors-custom/416.http
errorfile 417 /etc/haproxy/errors-custom/417.http
errorfile 418 /etc/haproxy/errors-custom/418.http
errorfile 421 /etc/haproxy/errors-custom/421.http
errorfile 422 /etc/haproxy/errors-custom/422.http
errorfile 423 /etc/haproxy/errors-custom/423.http
errorfile 424 /etc/haproxy/errors-custom/424.http
errorfile 425 /etc/haproxy/errors-custom/425.http
errorfile 426 /etc/haproxy/errors-custom/426.http
errorfile 428 /etc/haproxy/errors-custom/428.http
errorfile 429 /etc/haproxy/errors-custom/429.http
errorfile 431 /etc/haproxy/errors-custom/431.http
errorfile 451 /etc/haproxy/errors-custom/451.http
errorfile 500 /etc/haproxy/errors-custom/500.http
errorfile 501 /etc/haproxy/errors-custom/501.http
errorfile 502 /etc/haproxy/errors-custom/502.http
errorfile 503 /etc/haproxy/errors-custom/503.http
errorfile 504 /etc/haproxy/errors-custom/504.http
errorfile 505 /etc/haproxy/errors-custom/505.http
errorfile 506 /etc/haproxy/errors-custom/506.http
errorfile 507 /etc/haproxy/errors-custom/507.http
errorfile 508 /etc/haproxy/errors-custom/508.http
errorfile 510 /etc/haproxy/errors-custom/510.http
errorfile 511 /etc/haproxy/errors-custom/511.http
```
# Installation PFSense
1. Open your HAProxy configration page
2. Open the tab `FILES`
3. Add a new entry
4. name it `ErrorPFSense`
5. Paste the contents of `PFSense.http`
6. Hit Save
7. Go to your `Frondend` and open the fontend that you want to change
8. Scroll down to `Error files` and add all the error codes you want to support with `ErrorPFSense` as the error page
9. Hit Save
10. Apply Changes
