# Docker Dev Environment for Arm None Eabi with CMAKE

The base image is based on the simple [alpine_glibc_gcc-arm-none-eabi](https://github.com/Tech4Race/alpine_glibc_gcc-arm-none-eabi),
where cmake tool is added.

## Usage Example

This image is intended to be a base image for your development environment, so you may use it in different ways :

### Embedded your source code inside a new image

```Dockerfile
FROM tech4/alpine_glibc_gcc-arm-none-eabi_cmake

COPY ./my_app /home

```

```sh
$ docker build -t my_app .
```

### Mount dynamically your source code inside the base image

You can also use it always executed to compile manually from container commande line:

```sh
$ docker run -it --rm -v "$PWD":/home tech4/alpine_glibc_gcc-arm-none-eabi_cmake
/home # make
```
