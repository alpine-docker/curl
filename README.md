# docker-curl
Alpine-based image with just curl

NOTES: the original upstream https://github.com/appropriate/docker-curl is in read-only (archived statue), its images used base image of `alpine:3.7`, and are 4 years old now, vulnerabilities in its image, which is risk to use it. 

This repo will manage with latest alpine version, but must pass the trivy scan. 

## Usage

```console
$ docker run --rm alpine/curl:3.14 -fsSL https://www.google.com/
```

Or use it as alias command

```
$ alias curl="docker run --rm alpine/curl:3.14"

$ curl -fsSL https://www.google.com/
```

## Tags

* `alpine/curl:3.14`: based on `alpine` base image version

## Scan passed

The image is passed the trivy scan, you can run command to confirm

```
$ docker pull alpine/curl:3.14

$ docker run --rm -v /var/run/docker.sock:/var/run/docker.sock \
    -v $HOME/Library/Caches:/root/.cache/  aquasec/trivy alpine/curl:3.14

2021-12-06T00:11:14.187Z	INFO	Detected OS: alpine
2021-12-06T00:11:14.187Z	INFO	Detecting Alpine vulnerabilities...
2021-12-06T00:11:14.199Z	INFO	Number of language-specific files: 0

alpine/curl:3.14 (alpine 3.14.3)
================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

Currently base image `alpine:3.15` can't pass the scan.

## License

Copyright © 2015 Appropriate Computing

All contents licensed under the [MIT License](LICENSE)
