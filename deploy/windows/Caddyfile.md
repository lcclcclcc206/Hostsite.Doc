仅作为参考

```Caddyfile
{
    log {
        output file ./CaddyServer/log_caddy {
            roll_size 1MiB
            roll_keep_for 720h
        }
        format json
    }
}

:8880 {
    handle /api/filebrowser {
        uri strip_prefix /api/filebrowser
        reverse_proxy 127.0.0.1:8188
    }
    handle /api/filebrowser/* {
        uri strip_prefix /api/filebrowser
        reverse_proxy 127.0.0.1:8188
    }
    handle {
        root * `./WebUI`
        try_files {path} /index.html
        file_server
    }
    log {
        output file ./CaddyServer/log_server {
            roll_size 1MiB
            roll_keep_for 720h
        }
        format json
    }
}
```

