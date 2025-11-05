# cAdvisor-starter
repository for google cAdvisor start

## cAdvisor Repository
https://github.com/google/cadvisor

## Run as Docker
```
VERSION=v0.53.0 # use the latest release version from https://github.com/google/cadvisor/releases
sudo docker run \
  --volume=/:/rootfs:ro \
  --volume=/var/run:/var/run:ro \
  --volume=/sys:/sys:ro \
  --volume=/var/lib/docker/:/var/lib/docker:ro \
  --volume=/dev/disk/:/dev/disk:ro \
  --publish=8080:8080 \
  --detach=true \
  --name=cadvisor \
  --privileged \
  --device=/dev/kmsg \
  gcr.io/cadvisor/cadvisor:$VERSION
```

## Build and Run
```
# cAdvisor requires Go 1.14 to build.
# download source
go get -d github.com/google/cadvisor

# build from source directory
$GOPATH/src/github.com/google/cadvisor $ make build
```
