# Local AI

**Local AI** is an open-source Docker Compose template designed to swiftly initialize a comprehensive local AI and low-code development environment.

### What’s included

✅ [**Self-hosted n8n**](https://n8n.io/) - Low-code platform with over 400
integrations and advanced AI components

✅ [**Ollama**](https://ollama.com/) - Cross-platform LLM platform to install
and run the latest local LLMs

✅ [**Qdrant**](https://qdrant.tech/) - Open-source, high performance vector
store with an comprehensive API

✅ [**Nginx**](https://www.nginx.com/) - A high-performance web server that acts as a reverse proxy, load balancer, and HTTP cache.

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

1. Open <https://localhost/> in your browser to set up n8n. You’ll only
   have to do this once.
2. If this is the first time you’re running the workflow, you may need to deploy some models into Ollama.
   To do so, visit <https://ollama.com/search> and search for your model. 
   Then run the following command to deploy:
   ```bash
   docker exec ollama-local ollama pull model_name (ex: llama3.2)
   ```

To open n8n at any time, visit <https//localhost/> in your browser.

## Upgrading

```bash
docker compose down
docker compose pull
docker compose up -d
```

## Tips and Tricks

### Exporting Workflows and Credentials

```bash
docker exec -u node -it <n8n-container-name> n8n export:workflow --all --output=/home/node/exported-workflows.json
docker exec -u node -it <n8n-container-name> n8n export:credentials --all --output=/home/node/exported-credentials.json
```

### Copying files from the Docker container to the local machine

```bash
docker cp <n8n-container-name>:/home/node/exported-workflows.json ./exported-workflows.json
docker cp <n8n-container-name>:/home/node/exported-credentials.json ./exported-credentials.json
```

### Copying files from the local machine to the new Docker container

```bash
docker cp ./exported-credentials.json n8n-local:/home/node/
docker cp ./exported-workflows.json n8n-local:/home/node/
```

### Importing Workflows and Credentials

```bash
docker exec -u node -it <n8n-container-name> n8n import:credentials --input=/home/node/exported-credentials.json && n8n import:workflow --input=/home/node/exported-workflows.json
```
