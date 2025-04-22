# Build-LLM-model-using-ollama-and-Docker
# Open WebUI 👋  

**Open WebUI** is a powerful, extensible, and offline-capable self-hosted platform for working with Large Language Models (LLMs). It seamlessly integrates with **Ollama**, **OpenAI-compatible APIs**, and provides built-in features for **RAG (Retrieval Augmented Generation)**, **Python function calling**, **plugin support**, and more.


## 🌟 Key Features

- 🚀 **Quick Setup**: Deploy effortlessly using Python `pip`, Docker, or Kubernetes (via `kubectl`, Helm, or Kustomize).
- 🤖 **Model Flexibility**: Supports Ollama and OpenAI APIs, and connects with services like GroqCloud, LMStudio, Mistral, OpenRouter, and more.
- 🔐 **Role-Based Access Control (RBAC)**: Create user roles with custom permissions to maintain security and user-specific access.
- 📱 **Responsive and PWA**: Optimized for desktop and mobile; install as a Progressive Web App for offline access.
- 🧠 **Local RAG Support**: Load documents into your chat environment for context-aware conversation via RAG.
- ✍️ **Markdown & LaTeX**: Full support for Markdown formatting and LaTeX math rendering.
- 🎤 **Voice/Video Chat**: Built-in support for hands-free communication via voice and video.
- 🎨 **Image Generation**: Integrate with tools like ComfyUI, AUTOMATIC1111, and DALL·E for image generation.
- 🐍 **Native Python Integration**: Write and execute custom Python functions directly in the chat.
- 🌐 **Web Browsing & Search**: Inject real-time web search results from SearXNG, Brave, Bing, and more into conversations.
- 🌍 **Multilingual UI**: Internationalized interface with community-driven language support.
- 🧩 **Plugin System**: Extend functionality.
- 📈 **Monitoring & Rate Limiting**: Track usage, apply limits, and integrate with tools like Langfuse.

Explore more features in the [official documentation](https://docs.openwebui.com/features).

---

## 🔧 Installation Options

### 🔹 Option 1: Install via pip (Python 3.11)

```bash
pip install open-webui
open-webui serve
```

**Access at: [http://localhost:8080](http://localhost:8080)**

---

### 🔹 Option 2: Install via Docker

> 📌 Ensure you mount the database volume using `-v open-webui:/app/backend/data` to prevent data loss.

**Basic Docker Command (with Ollama installed locally):**
```bash
docker run -d -p 3000:8080 \
--add-host=host.docker.internal:host-gateway \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:main
```

**Remote Ollama Server:**
```bash
docker run -d -p 3000:8080 \
-e OLLAMA_BASE_URL=https://your-ollama-server.com \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:main
```

**With NVIDIA GPU Support (CUDA):**
```bash
docker run -d -p 3000:8080 \
--gpus all \
--add-host=host.docker.internal:host-gateway \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:cuda
```

**Using Only OpenAI API:**
```bash
docker run -d -p 3000:8080 \
-e OPENAI_API_KEY=your_secret_key \
-v open-webui:/app/backend/data \
--name open-webui --restart always \
ghcr.io/open-webui/open-webui:main
```

