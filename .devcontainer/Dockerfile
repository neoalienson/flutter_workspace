# See here for image contents: https://github.com/devcontainers/images/tree/main/src/universal
FROM mcr.microsoft.com/devcontainers/universal:latest

# Install Flutter SDK
ARG FLUTTER_VERSION="3.32.8"
RUN wget https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && tar xf flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && rm flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && mv flutter /opt/flutter

ENV PATH="/opt/flutter/bin:${PATH}"

# Run flutter doctor to download dependencies and verify installation
RUN flutter doctor
