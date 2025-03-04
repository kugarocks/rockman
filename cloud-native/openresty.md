# Openresty

## Path

```bash {copyable}
/usr/local/openresty
```

---

## Quick Start

```bash {copyable}
nginx -p `pwd`/ -c conf/nginx.conf
```

```bash {copyable}
mkdir logs/ conf/
```

```bash {copyable}
worker_processes  1;
error_log logs/error.log;
events {
    worker_connections 1024;
}
http {
    server {
        listen 8080;
        location / {
            default_type text/html;
            content_by_lua_block {
                ngx.say("<p>hello, world</p>")
            }
        }
    }
}
```

---

## Resty

```bash {copyable}
resty -e 'print("hello, world")'
```
