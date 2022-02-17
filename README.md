# NGINX PHP-FPM in separate Pods

## Purpose

This is a simple PHP application served by a php-fpm container behind nginx.

## Scenario

- php-fpm is running completely decoupled form nginx as a separate Pod
- it holds its PHP application in /app.
- PHP application comes from a config map and is mounted as a filemount to phpfpm pod.
- nginx only send its *.php file requests via port 9000 to php-fpm container.

## How to use

### Deploy

`kubectl apply -f .`

Create a port-forward:

`kubectl -n demo  port-forward nginx 8080:80`

### Access

Browse: http://localhost:8080

### Uninstall

`kubectl delete -f .`

## Reference

https://mailman.nginx.org/pipermail/nginx/2008-November/008311.html

## Info

Author: c.hoerl@syseleven.de
