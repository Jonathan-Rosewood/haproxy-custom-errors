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
errorfile 403 /etc/haproxy/errors-custom/403.http
errorfile 408 /etc/haproxy/errors-custom/408.http
errorfile 500 /etc/haproxy/errors-custom/500.http
errorfile 502 /etc/haproxy/errors-custom/502.http
errorfile 503 /etc/haproxy/errors-custom/503.http
errorfile 504 /etc/haproxy/errors-custom/504.http
```
