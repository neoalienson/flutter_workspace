# Flutter Web Development Codespace

This GitHub Codespace is configured for Flutter web application development. It includes:

- **Flutter SDK**: The latest stable version of Flutter is pre-installed.
- **VS Code Extensions**: Essential extensions for Flutter/Dart development, Prettier, and Cline are pre-installed.
- **Common Utilities**: Basic development utilities are available.

## Getting Started

1.  **Launch Codespace**: Open this repository in a GitHub Codespace.
2.  **Create/Open Flutter Project**: Once the Codespace is ready, you can create a new Flutter project or open an existing one.
    ```bash
    flutter create --platforms web my_web_app
    cd my_web_app
    ```

## Running Flutter Web App

To run your Flutter web application on port 8080, you must explicitly specify the web device, port, and hostname. Use the following command:

```bash
flutter run -d web-server --web-port 8080 --web-hostname 0.0.0.0
```

The application will be accessible on port 8080 (forwarded automatically).

## Customization

-   **Flutter Version**: To change the Flutter version, modify the `FLUTTER_VERSION` argument in `.devcontainer/Dockerfile`.
-   **VS Code Extensions**: Add or remove extensions in the `customizations.vscode.extensions` section of `.devcontainer/devcontainer.json`.

## Cline Configuration (OpenAI Compatible)

To configure Cline with an OpenAI compatible API, you will need to do so through the VS Code UI after the Codespace has launched. 

1.  **Launch Codespace**: Open this repository in a GitHub Codespace.
2.  **Open VS Code Settings**: Go to `File > Preferences > Settings` (or `Code > Preferences > Settings` on macOS).
3.  **Search for Cline**: In the search bar, type "Cline" to filter the settings.
4.  **Configure API Key and Model**: Use the provided fields to enter your API key and select your desired model. The base URL for the OpenAI compatible API is `https://api-inference.modelscope.cn/v1/`. Refer to Cline's official documentation for specific setting names and values.

### Recommended Cline Models

**For Coding:**
- `Qwen/Qwen3-Coder-480B-A35B-Instruct` (Context Length: 262,144 tokens)
- `Qwen/Qwen3-Coder-30B-A3B-Instruct` (Context Length: 262,144 tokens)
- `Qwen/Qwen3-235B-A22B-Instruct-2507` (Context Length: 262,144 tokens)
- `deepseek-ai/DeepSeek-V3` (Context Length: 128,000 tokens)

**For Planning:**
- `Qwen/Qwen3-235B-A22B-Thinking-2507` (Context Length: 262,144 tokens)