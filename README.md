# docker-curl
Alpine-based image with just curl

## Usage

```console
$ docker run --rm alpine/curl -fsSL https://www.google.com/
```

## Tags

* `alpine/curl:3.14`: based on `alpine` base image version

## Scan passed

The image is passed the trivy scan, you can run command to confirm

```
docker pull alpine/curl:3.14

docker run --rm -v /var/run/docker.sock:/var/run/docker.sock \
    -v $HOME/Library/Caches:/root/.cache/  aquasec/trivy alpine/curl:3.14
```

Currently alpine:3.15 can't pass the scan.

## License

Copyright © 2015 Appropriate Computing

All contents licensed under the [MIT License](LICENSE)
