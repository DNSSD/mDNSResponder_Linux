# Devcontainer image for building/debugging mDNSResponder on Linux (mDNSPosix/Makefile, os=linux).
#
# Base: Microsoft's devcontainer "base" (Debian bookworm) which already provides a non-root
# "vscode" user with passwordless sudo, git, and common CLI tooling.
#
# Debian bookworm ships mbedTLS 2.28.x (libmbedtls-dev). The TLS shim (mDNSPosix/mbedtls.c) is
# being written to support both mbedTLS 2.x and 3.x; if you need 3.x, switch the base to
# mcr.microsoft.com/devcontainers/base:trixie (or an Ubuntu 24.04 image) instead.
FROM mcr.microsoft.com/devcontainers/base:bookworm

RUN apt-get update \
 && export DEBIAN_FRONTEND=noninteractive \
 && apt-get install -y --no-install-recommends \
        build-essential \
        make \
        bison \
        flex \
        libmbedtls-dev \
        gdb \
        iproute2 \
        iputils-ping \
        avahi-utils \
        ca-certificates \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*
