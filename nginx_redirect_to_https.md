To redirect all requests on http://mydomain.org to https://mydomain.org, add this Nginx config file:

```
server {
  listen 80;
  server_name _;
  return  301 https://mydomain.org$request_uri;
}
```
