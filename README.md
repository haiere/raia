# RAIA

A symmetric AI chat assistant with multi-provider support, running entirely in your browser.

RAIA is a client-side AI chat interface that connects to multiple large language model providers including OpenRouter, OpenAI, Perplexity, Claude (Anthropic), Gemini (Google), and Mistral. It provides a unified chat experience with local history storage, model selection, and configurable generation parameters.

All communication with AI providers happens directly from your browser. No server is involved—your API keys and conversations stay on your device.

---

## Features

- Multi-provider support — Connect to OpenRouter, OpenAI, Perplexity, Claude, Gemini, and Mistral from a single interface.
- Model selection — Choose from provider-specific model lists or enter a custom model ID.
- Local chat history — Conversations are stored in your browser's `localStorage` and persist between sessions.
- Adjustable generation parameters — Control temperature and maximum token output via sliders.
- Keyboard shortcuts — Send with Enter, new line with Shift+Enter, focus with Ctrl+K, new chat with Ctrl+N, history with Ctrl+H.
- Dark / light theme — Toggle between themes manually or follow system preference.
- Suggestion chips — Quick-start prompts for common use cases.
- Copy and regenerate — Each assistant message includes copy and regenerate buttons.
- No tracking, no telemetry — The application does not collect any usage data.

---

## Requirements

- A modern web browser with JavaScript enabled (Chrome, Firefox, Edge, Safari, or similar).
- An API key for at least one supported provider.
- The page is a single HTML file and requires no installation.

---

## Installation

RAIA is a single-page application. To use it:

1. Open the hosted URL in your browser.
2. Alternatively, download the `index.html` file and open it locally.

To host the application yourself, place the file on any static web server. All styles, icons, and scripts are self-contained.

---

## Usage

### Step-by-step

1. Configure a provider — Click the "Setup API" button in the header to open the settings panel.
2. Select a provider — Choose from OpenRouter, OpenAI, Perplexity, Claude, Gemini, or Mistral.
3. Enter your API key — Paste your key in the API Key field. You can choose to remember it locally.
4. Select a model — Choose from the provider's model list or type a custom model ID.
5. Connect — Click "Connect" to confirm your settings. A status indicator will show "Connected."
6. Start chatting — Type a message and press Enter to send.
7. Adjust parameters — Use the temperature and max tokens sliders to control generation behaviour.
8. Access history — Click the history icon to view, load, or delete previous conversations.

### Supported providers and models

| Provider | Default models (examples) |
|---|---|
| OpenRouter | `claude-sonnet-5`, `gpt-5.6`, `gemini-3.5-flash`, `llama-4-maverick` |
| OpenAI | `gpt-5.6`, `gpt-4o`, `gpt-4o-mini` |
| Perplexity | `sonar`, `sonar-pro`, `sonar-reasoning-pro` |
| Claude (Anthropic) | `claude-sonnet-5`, `claude-opus-4-8`, `claude-haiku-4-5` |
| Gemini (Google) | `gemini-3.5-flash`, `gemini-3.1-pro-preview` |
| Mistral | `mistral-large-latest`, `mistral-small-latest`, `codestral-latest` |

---

## Configuration

### Settings panel

The settings panel provides the following options:

- Provider — Dropdown to select the AI provider.
- Model — Text input with datalist support for provider-specific models.
- API Key — Password input with a visibility toggle and optional persistence.
- Custom Base URL — Override the default API endpoint for the selected provider.
- CORS Proxy URL — Required for providers that block direct browser requests (OpenAI, Perplexity, Mistral). Use a worker or proxy service to forward requests.
- Temperature — Slider ranging from 0.0 to 2.0 (step 0.1).
- Max Tokens — Slider from 256 to 8192 (step 128).

### Advanced options

- Custom Base URL — Enter a custom endpoint if you are using a gateway or local service.
- CORS Proxy URL — Enter a proxy endpoint to handle requests for providers that do not support direct browser calls.

---

## Privacy and Security

- All API keys are stored locally in your browser's `localStorage` if you choose to remember them.
- Conversation history is stored locally and never sent to any third party.
- No analytics, tracking, or telemetry is collected.
- The application does not use cookies or external services beyond the AI provider APIs.

---

## Troubleshooting

- Connection fails — Verify your API key is correct and that the selected model is available for your provider.
- CORS errors with OpenAI, Perplexity, or Mistral — These providers block direct browser requests. Set a CORS Proxy URL in the advanced settings section.
- Model not found — Ensure the model ID is spelled correctly and is supported by the chosen provider.
- Rate limit errors — You may have exceeded your provider's rate limit. Wait a moment and try again.
- History not saving — Check that your browser allows `localStorage` and that you are not in private/incognito mode.

---

## Roadmap

Future improvements may include:

- Streaming responses.
- System prompt configuration.
- Export and import of chat history.
- Additional provider integrations.
- Response caching and offline support.

---

## Contributing

Contributions are welcome. Areas for improvement include:

- Support for additional AI providers.
- Enhanced markdown rendering with syntax highlighting.
- Improved accessibility and internationalisation.
- Performance optimisations.

Please fork the repository and submit a pull request with a clear description of your changes.

---

## Development Setup

The application is a single `index.html` file. To develop:

- Edit the file directly.
- Test by opening it in a browser.
- No build tools or compilation steps are required.

For local hosting, use any static server:

```bash
python -m http.server
```

or

```bash
npx serve
```

---

## License

RAIA is released under the MIT license. See the `LICENSE` file for full details.

---

## Author and Support

Developed and maintained by Haiere and HajirStudio. For bug reports, feature requests, or questions, please use the project issue tracker or contact via the repository.

---

Last updated: 2026
