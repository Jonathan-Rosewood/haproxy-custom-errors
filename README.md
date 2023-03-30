![preview](https://media.giphy.com/media/3ohhwfW9OgNMwDLZra/giphy.gif)

# Haproxy Custom Errors
Custom http error pages for haproxy

# Error Code Definitions
400 Bad Request:  
	The server cannot or will not process the request due to an apparent client error (e.g., malformed request syntax, size too large, invalid request message framing, or deceptive request routing)  
403 Forbidden:  
	The request contained valid data and was understood by the server, but the server is refusing action. This may be due to the user not having the necessary permissions for a resource or needing an account of some sort, or attempting a prohibited action (e.g. creating a duplicate record where only one is allowed). This code is also typically used if the request provided authentication by answering the WWW-Authenticate header field challenge, but the server did not accept that authentication. The request should not be repeated.  
408 Request Timeout:  
	The server timed out waiting for the request. According to HTTP specifications: "The client did not produce a request within the time that the server was prepared to wait. The client MAY repeat the request without modifications at any later time.  
500 Internal Server Error:  
	A generic error message, given when an unexpected condition was encountered and no more specific message is suitable.  
502 Bad Gateway:  
	The server was acting as a gateway or proxy and received an invalid response from the upstream server.  
503 Service Unavailable:  
	The server cannot handle the request (because it is overloaded or down for maintenance). Generally, this is a temporary state.  
504 Gateway Timeout:  
	The server was acting as a gateway or proxy and did not receive a timely response from the upstream server.  

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
