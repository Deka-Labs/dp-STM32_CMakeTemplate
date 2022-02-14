# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.217.4/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version (use hirsuite or bionic on local arm64/Apple Silicon): hirsute, focal, bionic
ARG VARIANT="hirsute"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# Install packages
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends gdb-multiarch binutils-arm-none-eabi gcc-arm-none-eabi libnewlib-arm-none-eabi cmake build-essential wget openocd stlink-tools 

# STM32F4 and STM32F3 Package
RUN  wget https://github.com/STMicroelectronics/STM32CubeF4/archive/refs/tags/v1.26.2.tar.gz \
    && tar -xf ./v1.26.2.tar.gz -C /opt \
    && mv /opt/STM32CubeF4-1.26.2 /opt/STM32CubeF4

RUN  wget https://github.com/STMicroelectronics/STM32CubeF3/archive/refs/tags/v1.11.3.tar.gz \
    && tar -xf ./v1.11.3.tar.gz -C /opt \
    && mv /opt/STM32CubeF3-1.11.3 /opt/STM32CubeF3

# Set location
ENV STM32_CUBE_F4_PATH=/opt/STM32CubeF4
ENV STM32_CUBE_F3_PATH=/opt/STM32CubeF3


