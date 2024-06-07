# UMD Varnish

This repo contains the umd-varnish, based on Wodby Varnish, and umd-varnish-logger, based on the official Varnish images.

### Building UMD Varnish for Kubernetes

```bash
cd umd-varnish
docker buildx build . --builder=kube -t docker.lib.umd.edu/umd-varnish:latest --push
```

### Building UMD Varnish Logger for Kubernetes

```bash
cd umd-varnish-logger
docker buildx build . --builder=kube -t docker.lib.umd.edu/umd-varnish-logger:latest --push
```
