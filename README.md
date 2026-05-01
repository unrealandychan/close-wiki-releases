# close-wiki

> Agentic repo-to-wiki: scan any repository into a portable SQLite knowledge store with wiki pages, diagrams, and grounded Q&A.

---

## Installation

### Homebrew (macOS / Linux) — Recommended

```bash
brew tap unrealandychan/tap
brew install close-wiki
```

### Download Binary

Download the latest release from [GitHub Releases](https://github.com/unrealandychan/close-wiki-releases/releases).

| Platform | Architecture | File |
|----------|-------------|------|
| macOS | Apple Silicon (M1/M2/M3) | `close-wiki_darwin_arm64.tar.gz` |
| macOS | Intel | `close-wiki_darwin_amd64.tar.gz` |
| Linux | x86_64 | `close-wiki_linux_amd64.tar.gz` |
| Linux | ARM64 | `close-wiki_linux_arm64.tar.gz` |
| Windows | x86_64 | `close-wiki_windows_amd64.zip` |

Extract and move to your `$PATH`:

```bash
# macOS (Apple Silicon)
tar -xzf close-wiki_darwin_arm64.tar.gz
mv close-wiki /usr/local/bin/
```

---

## Quick Start

```bash
# Scan a repository and generate wiki
close-wiki scan --path /path/to/repo

# Serve the wiki locally (opens in browser)
close-wiki serve --path /path/to/repo

# Ask questions about the codebase (interactive chat mode)
close-wiki ask --path /path/to/repo -i

# Ask a single question
close-wiki ask --path /path/to/repo "How does the authentication work?"

# Update wiki after code changes
close-wiki update --path /path/to/repo

# Generate embeddings for semantic search
close-wiki embed --path /path/to/repo
```

---

## Commands

| Command | Description |
|---------|-------------|
| `scan` | Scan repository and generate wiki pages |
| `serve` | Start local web server to browse the wiki |
| `ask` | Ask questions about the codebase (supports `-i` interactive chat mode) |
| `update` | Incrementally update wiki after code changes |
| `embed` | Generate embeddings for semantic search (RAG) |

---

## Supported Languages

- Go
- Python
- TypeScript / JavaScript
- Rust
- Java
- Ruby
- C / C++

---

## Configuration

Create a `config.yml` in your project root:

```yaml
llm:
  provider: openai
  model: gpt-4o
  api_key: your-api-key

output_dir: .wiki
```

---

## Interactive Chat Mode

`close-wiki ask` supports a full interactive REPL with conversation history:

```
╭─────────────────────────────────────────╮
│  close-wiki ask  •  /path/to/repo       │
│  Type your question. Ctrl+C or /quit    │
╰─────────────────────────────────────────╯

You ▸ How is the database layer structured?
Assistant ▸ The database layer uses ...

You ▸ /clear   # reset history
You ▸ /quit    # exit
```

---

## Links

- 🏠 [Homepage / Source](https://github.com/unrealandychan/close-wiki) *(private)*
- 📦 [Releases](https://github.com/unrealandychan/close-wiki-releases/releases)
- 🍺 [Homebrew Tap](https://github.com/unrealandychan/homebrew-tap)
