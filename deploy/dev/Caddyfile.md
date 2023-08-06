仅作为参考

```Caddyfile
{
    log {
        output file ./log/caddy {
            roll_size 1MiB
            roll_keep_for 720h
        }
        format json
    }
}

:6660 {
    handle /api/filebrowser {
        uri strip_prefix /api/filebrowser
        reverse_proxy 127.0.0.1:6166
    }
    handle /api/filebrowser/* {
        uri strip_prefix /api/filebrowser
        reverse_proxy 127.0.0.1:6166
    }
    handle {
#        root * `C:\Users\lcclcclcc206\Desktop\Task\HostSite\WebUI`
#        try_files {path} /index.html
#        file_server
    }
    log {
        output file ./log/server {
            roll_size 1MiB
            roll_keep_for 720h
        }
        format json
    }
}
```

