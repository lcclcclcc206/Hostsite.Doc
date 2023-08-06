仅作为参考

```Caddyfile
{
    log {
        output file "/data/data/com.termux/files/home/Hostsite/CaddyServer/logcaddy" {
            roll_size 1MiB
            roll_keep_for 720h
        }
        format json
	level info
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
	    root * "/data/data/com.termux/files/home/Hostsite/WebUI/"
        try_files {path} /index.html
        file_server
    }
    log {
        output file "/data/data/com.termux/files/home/Hostsite/CaddyServer/logserver" {
            roll_size 1MiB
            roll_keep_for 720h
        }
        format json
	level info
    }
}
```

