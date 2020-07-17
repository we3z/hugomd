---
​---
title: "Nginx代理调试 域名/api/abc->域名/abc"
date: 2020-07-17T22:11:07+08:00
type: it
draft: false
​---
---

# Nginx代理调试 域名/api/abc->域名/abc

今天在配合前段完成工作的时候，遇到一个问题

用 nginx 将 IP 地址 /api/abc 代理到 IP 地址 /abc

```sh
server {
	listen 8080;
	root /abc/def;
	location / {
		index index.html;
	}
	location /api/ {
		proxy_pass http://127.0.0.1:8080/;
	}
}
```

