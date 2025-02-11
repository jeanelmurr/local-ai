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

### Running Local AI using Docker Compose

```bash
docker compose up -d
```

## ⚡️ Quick start and usage

The core of the Local AI is a Docker Compose file, pre-configured with network and storage settings, minimizing the need for additional installations.
After completing the installation steps above, simply follow the steps below to get started.

1. Open <http://localhost:5678/> in your browser to set up n8n. You’ll only
   have to do this once.
2. If this is the first time you’re running the workflow, you may need to deploy some models into Ollama.
   To do so, visit <https://ollama.com/search> and search for your model. 
   Then run the following command to deploy:
   ```bash
   docker exec ollama-local ollama pull 'model_name' (ex: llama3.2)
   ```

To open n8n at any time, visit <http://localhost:5678/> in your browser.

## Upgrading

```bash
docker compose down
docker compose pull
docker compose up -d
```
