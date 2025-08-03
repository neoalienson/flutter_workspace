# Flutter Web Development Codespace

This GitHub Codespace is configured for Flutter web application development. It includes:

- **Flutter SDK**: The latest stable version of Flutter is pre-installed.
- **VS Code Extensions**: Essential extensions for Flutter/Dart development, Prettier, and Cline are pre-installed.
- **Common Utilities**: Basic development utilities are available.

## Getting Started

1.  **Launch Codespace**: Open this repository in a GitHub Codespace.
2.  **Create/Open Flutter Project**: Once the Codespace is ready, you can create a new Flutter project or open an existing one.
    ```bash
    flutter create my_web_app
    cd my_web_app
    ```
3.  **Run Web App**: To run your Flutter web application, use the following command:
    ```bash
    flutter run -d web-server
    ```
    The application will be accessible on port 8080 (forwarded automatically).

## Customization

-   **Flutter Version**: To change the Flutter version, modify the `FLUTTER_VERSION` argument in `.devcontainer/Dockerfile`.
-   **VS Code Extensions**: Add or remove extensions in the `customizations.vscode.extensions` section of `.devcontainer/devcontainer.json`.
-   **Cline Settings**: Configure Cline extension settings in the `customizations.vscode.settings` section of `.devcontainer/devcontainer.json`.

## Cline Configuration (OpenAI Compatible)

To configure Cline with an OpenAI compatible API, you can add the following settings to the `customizations.vscode.settings` section of your `.devcontainer/devcontainer.json` file. Remember to replace `YOUR_API_KEY` with your actual API key.

```json
"cline.openai.baseUrl": "https://api-inference.modelscope.cn/v1/",
"cline.openai.apiKey": "YOUR_API_KEY",
"cline.openai.model": "Qwen/Qwen3-Coder-480B-A35B-Instruct",
"cline.openai.models": [
    {
        "id": "Qwen/Qwen3-Coder-480B-A35B-Instruct",
        "name": "Qwen/Qwen3-Coder-480B-A35B-Instruct",
        "contextLength": 262144
    },
    {
        "id": "Qwen/Qwen3-Coder-30B-A3B-Instruct",
        "name": "Qwen/Qwen3-Coder-30B-A3B-Instruct",
        "contextLength": 262144
    },
    {
        "id": "Qwen/Qwen3-235B-A22B-Instruct-2507",
        "name": "Qwen/Qwen3-235B-A22B-Instruct-2507",
        "contextLength": 262144
    },
    {
        "id": "deepseek-ai/DeepSeek-V3",
        "name": "deepseek-ai/DeepSeek-V3",
        "contextLength": 128000
    },
    {
        "id": "Qwen/Qwen3-235B-A22B-Thinking-2507",
        "name": "Qwen/Qwen3-235B-A22B-Thinking-2507",
        "contextLength": 262144
    }
]
```

**Recommended Models for Coding:**
- `Qwen/Qwen3-Coder-480B-A35B-Instruct`
- `Qwen/Qwen3-Coder-30B-A3B-Instruct`
- `Qwen/Qwen3-235B-A22B-Instruct-2507`
- `deepseek-ai/DeepSeek-V3`

**Recommended Model for Planning:**
- `Qwen/Qwen3-235B-A22B-Thinking-2507`