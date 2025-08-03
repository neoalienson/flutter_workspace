# GitHub Codespace Setup Details

This document outlines the configuration for the GitHub Codespace designed for Flutter web development.

## `devcontainer.json` Configuration

- **Base Image**: Uses a custom Dockerfile for image building.
- **Features**: Includes `ghcr.io/devcontainers/features/common-utils:2` for common utilities.
- **Port Forwarding**: Forwards port `8080` for web applications.
- **Post-Create Command**: No specific commands are run after container creation, as Flutter setup is handled during the prebuild.
- **VS Code Customizations**:
    - **Extensions**: Pre-installs essential extensions:
        - `Dart-Code.flutter`
        - `Dart-Code.dart-code`
        - `esbenp.prettier-vscode`
        - `saoudrizwan.claude-dev` (Cline extension)
    - **Settings**: Includes placeholder settings for Cline:
        ```json
        "your.cline.model.setting.key": "your-model-name"
        ```

## `Dockerfile` Configuration

This Dockerfile builds the custom image for the Codespace, ensuring Flutter is available during the prebuild phase.

- **Base Image**: `mcr.microsoft.com/devcontainers/universal:latest`
- **Flutter Installation**:
    - **Version**: Installs Flutter version `3.32.8`.
    - **Download**: Downloads the Flutter SDK from `https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_3.32.8-stable.tar.xz`.
    - **Path**: Adds `/opt/flutter/bin` to the system's `PATH`.
- **User and Permissions**:
    - Changes ownership of `/opt/flutter` to `1000:1000` (default UID/GID for non-root user in Dev Containers).
    - Grants write permissions to the owner of `/opt/flutter` (`chmod -R u+w /opt/flutter`).
    - Switches to the non-root user (`_REMOTE_USER`, typically `codespace` or `vscode`) for subsequent commands.
- **Flutter Configuration**:
    - Disables Linux and Android desktop development using `flutter config --no-enable-linux-desktop` and `flutter config --no-enable-android`.
    - Adds `/opt/flutter` to Git's safe directories for the non-root user (`git config --global --add safe.directory /opt/flutter`).
- **Precache and Doctor**:
    - Runs `flutter precache` to download necessary development binaries during the prebuild.
    - Runs `flutter doctor` to verify the Flutter setup during the prebuild.
