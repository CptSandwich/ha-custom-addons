# Pull evcc binary from our custom fork
FROM ghcr.io/cptsandwich/evcc:latest AS evcc_source

# Build the actual add-on image using HA's base
ARG BUILD_FROM
FROM ${BUILD_FROM}

# Runtime dependencies
RUN apk add --no-cache tzdata ca-certificates

# Copy the evcc binary from our custom image
COPY --from=evcc_source /usr/local/bin/evcc /usr/local/bin/evcc

# Copy s6 service scripts
COPY rootfs /
