Fig + Docker symlink testcase
=============================

This is a testcase for an issue where relative symlinks aren't `COPY`'d over
when building a Docker container using Fig. If we start the container using
Docker directly, the symlinks work as expected.

### Starting the container using Docker

* `docker build -t docker-symlink-example example/`
* `docker run -t -i docker-symlink-example bash`
* See that there is a symlink to `/src/b/` in `/src/a/`

### Starting the container using Fig

* `fig up`
* `fig run example bash`
* See that there is no symlink to `/src/b/` in `/src/a/`
