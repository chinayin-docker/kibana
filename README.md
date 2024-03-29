# Kibana Image

[![Docker Image CI](https://github.com/chinayin-docker/kibana/actions/workflows/ci.yml/badge.svg?event=schedule)](https://github.com/chinayin-docker/kibana/actions/workflows/ci.yml)
![Docker Image Version (latest semver)](https://img.shields.io/docker/v/chinayin/kibana?sort=semver)
![Docker Image Size (latest semver)](https://img.shields.io/docker/image-size/chinayin/kibana?sort=semver)
![Docker Pulls](https://img.shields.io/docker/pulls/chinayin/kibana)

Kibana is your window into the Elastic Stack. Specifically, it's a browser-based analytics and search dashboard for
Elasticsearch.

### Supported tags and respective `Dockerfile` links

![](https://img.shields.io/docker/v/chinayin/kibana/7)

### Image Variants

- `kibana:<version>`

### Usage

You can use the image directly, e.g.

```
docker run --rm -it chinayin/kibana:8
```

The images are built daily and have the security release enabled, so will contain any security updates released more
than 24 hours ago.

You can also use the images as a base for your own Dockerfile:

```
FROM chinayin/kibana:8
```
