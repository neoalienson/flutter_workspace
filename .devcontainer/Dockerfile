# See here for image contents: https://github.com/devcontainers/images/tree/main/src/universal
FROM mcr.microsoft.com/devcontainers/universal:latest

# Install Flutter SDK
ARG FLUTTER_VERSION="3.32.8"
RUN wget https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && tar xf flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && rm flutter_linux_${FLUTTER_VERSION}-stable.tar.xz \
    && mv flutter /opt/flutter

ENV PATH="/opt/flutter/bin:${PATH}"

# Switch to non-root user and change ownership of Flutter directory
USER vscode
RUN sudo chown -R vscode:vscode /opt/flutter

# Add Flutter directory to Git's safe directories for the vscode user
RUN git config --global --add safe.directory /opt/flutter

# Run flutter doctor to download dependencies and verify installation
RUN flutter doctor
