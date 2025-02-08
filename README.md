# Local AI

**Local AI** is an open-source Docker Compose template designed to swiftly initialize a comprehensive local AI and low-code development environment.

### What’s included

✅ [**Self-hosted n8n**](https://n8n.io/) - Low-code platform with over 400
integrations and advanced AI components

✅ [**Ollama**](https://ollama.com/) - Cross-platform LLM platform to install
and run the latest local LLMs

## Installation

### Cloning the Repository

```bash
git clone https://github.com/jeanelmurr/local-ai.git
cd local-ai
```

### Running n8n using Docker Compose

```bash
docker compose up
```

After you followed the quick start set-up below, change the Ollama credentials
by using `http://host.docker.internal:11434/` as the host.

## ⚡️ Quick start and usage

The core of the Local AI is a Docker Compose file, pre-configured with network and storage settings, minimizing the need for additional installations.
After completing the installation steps above, simply follow the steps below to get started.

1. Open <http://localhost:5678/> in your browser to set up n8n. You’ll only
   have to do this once.
2. If this is the first time you’re running the workflow, you may need to wait
   until Ollama finishes downloading Llama3.2. You can inspect the docker
   console logs to check on the progress.

To open n8n at any time, visit <http://localhost:5678/> in your browser.

## Upgrading

```bash
docker compose pull
docker compose create && docker compose up
```
