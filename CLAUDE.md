# MemGPT

Create perpetual chatbots with self-editing memory. Open-source framework for building LLM agents with long-term memory and context management.

## Purpose

MemGPT (now Letta) is a system for building LLM applications with unlimited context and long-term memory. Enables chatbots that remember past conversations, chat with local files/databases, and maintain persistent state across sessions. Designed for researchers and developers building stateful AI agents.

## Tech Stack

- **Language**: Python
- **Core**: PyTorch, Transformers
- **LLMs**: OpenAI, Local models (via Ollama), AutoGen integration
- **Database**: SQLite (local), PostgreSQL (optional)
- **Framework**: FastAPI (for API server)
- **Testing**: pytest
- **Docs**: MkDocs, ReadTheDocs

## Architecture

MemGPT provides a memory management layer that sits between the user and LLM, allowing agents to:
- Store long-term memories beyond context window limits
- Retrieve relevant context dynamically
- Edit their own memory state
- Interface with external data sources (files, SQL databases)

## Quick Start

```bash
# Install via pip
pip install pymemgpt

# Or install from source
poetry install

# Discord bot setup (fastest way to try)
# Join Discord: https://discord.gg/9GEQrxmVyE
# Message "MemGPT Bot" in #memgpt channel:
/profile   # Create profile
/key       # Enter OpenAI key
/create    # Create chatbot

# Local CLI
memgpt run

# With local LLMs (Ollama)
memgpt run --model ollama/llama2

# Python API
python main.py
```

## Key Files

- `memgpt/` - Core MemGPT library
  - `agent.py` - Agent implementation with memory
  - `memory.py` - Memory management system
  - `interface.py` - User interface abstractions
  - `persistence.py` - State persistence
- `db/` - Database schemas and migrations
- `docs/` - Documentation source
- `tests/` - Test suite
- `main.py` - Example entry point
- `pyproject.toml` - Poetry dependencies and metadata
- `mkdocs.yml` - Documentation configuration

## Features

- Unlimited conversation context via memory management
- Self-editing memory (agents can update their own memory)
- Chat with local documents (RAG-style retrieval)
- SQL database querying via natural language
- Discord bot integration
- Local LLM support (Ollama, etc.)
- AutoGen multi-agent integration
- REST API server

## Development Notes

- Uses Poetry for dependency management
- Memory is stored in a hierarchical system (core memory, archival, recall)
- Agents can use "functions" to edit their memory state
- Supports multiple LLM backends (OpenAI, local, Anthropic via plugins)
- Pre-commit hooks configured for code quality
- Documentation hosted on ReadTheDocs
- Originally research project from UC Berkeley, now maintained by Letta team
- Forked repository - check for upstream updates
