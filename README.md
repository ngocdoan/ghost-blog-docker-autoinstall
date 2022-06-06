# ghost-blog-docker-autoinstall
#### Bug: Setting url: to https in config.js causes a redirect loop #2796
```
https://github.com/TryGhost/Ghost/issues/2796
```
```
server {
        listen                          443 ssl spdy;

        location / {
            proxy_pass              http://localhost:8080;
            proxy_set_header        X-Real-IP $remote_addr;
            proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header        X-Forwarded-Proto https;
            proxy_set_header        Host $http_host;
            proxy_intercept_errors  on;
        }
}
```
