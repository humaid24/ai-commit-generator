# AI Commit Generator

A VSCode extension that stages all changes, diffs them, and auto-generates a commit message using any OpenAI-compatible LLM — filling it directly into the Source Control input box.

## Usage

1. Write your code
2. Click the **✨ sparkle button** in the Source Control panel title bar
3. The extension will:
   - Run `git add --all`
   - Get the staged diff
   - Send it to your configured LLM
   - Auto-fill the commit message box
4. Review the message and press **Commit** ✓

## Setup

Open **Settings** (`Cmd/Ctrl + ,`) and search for `aiCommit`:

| Setting                 | Description                             | Example                       |
| ----------------------- | --------------------------------------- | ----------------------------- |
| `aiCommit.apiBaseUrl`   | Base URL of your LLM API                | `https://api.deepseek.com/v1` |
| `aiCommit.apiKey`       | Your API key                            | `sk-...`                      |
| `aiCommit.model`        | Model name                              | `deepseek-chat`               |
| `aiCommit.systemPrompt` | Your commit message format instructions | (see default)                 |
| `aiCommit.maxDiffLines` | Truncate diffs longer than this         | `500`                         |

## Provider Examples

**DeepSeek**

```
apiBaseUrl: https://api.deepseek.com/v1
model: deepseek-chat
```

**Anthropic (via OpenAI-compatible proxy)**

```
apiBaseUrl: https://api.anthropic.com/v1
model: claude-sonnet-4-6
```

**OpenAI**

```
apiBaseUrl: https://api.openai.com/v1
model: gpt-4o
```

**Local Ollama**

```
apiBaseUrl: http://localhost:11434/v1
model: llama3
apiKey: (leave blank)
```

## Install (Development)

```bash
bun install
bun run compile
# Press F5 in VSCode to launch the Extension Development Host
```

To package as a `.vsix`:

```bash
bunx @vscode/vsce package
```
