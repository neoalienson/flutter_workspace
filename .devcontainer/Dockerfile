# See here for image contents: https://github.com/devcontainers/images/tree/main/src/universal
FROM mcr.microsoft.com/devcontainers/universal:latest

ARG _REMOTE_USER

# Install Flutter SDK
ARG FLUTTER_VERSION="3.32.8"
RUN wget -q https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && tar xf flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && rm flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && mv flutter /opt/flutter

ENV PATH="/opt/flutter/bin:${PATH}"

# Change ownership of Flutter directory to vscode user
RUN chown -R 1000:1000 /opt/flutter
RUN chmod -R a+rw /opt/flutter    

# Switch to non-root user
USER ${_REMOTE_USER}

# Add Flutter directory to Git's safe directories for the vscode user
RUN git config --global --add safe.directory /opt/flutter

# Disable Linux and Android desktop development
RUN flutter config --no-enable-linux-desktop
RUN flutter config --no-enable-android

# Precache Flutter artifacts
RUN flutter precache

# Run flutter doctor to download dependencies and verify installation
RUN flutter doctor



