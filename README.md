# Onvidio Universal AI Plugin (MCP)

This repository contains the client-side **Plugin Manifests and Skills** for the Onvidio MCP server. It acts as the connector that enables AI assistants (like ChatGPT, Antigravity, and Claude) to seamlessly interact with the remote Onvidio platform to draft video layouts, query data, and manage video generation workflows.

Since the actual MCP server logic is hosted remotely on the Onvidio backend, this repository purely serves as the client installation package. It is built on the universal open MCP standard, meaning its core logic and tools work across multiple AI ecosystems simultaneously.

## 📂 Repository Structure & Ecosystem Support

Because different AI clients have slightly different metadata requirements for their plugins, you will notice multiple configuration files in this repository. All of them point to the exact same remote MCP server (`https://app.onvidio.com/mcp`) and share the same core skills.

*   `skills/`: The universal instruction workflows and AI guidelines (compatible with all LLMs).

**Google Antigravity Files:**
*   `plugin.json`: The Antigravity plugin manifest.
*   `mcp_config.json`: The Antigravity MCP server connection configuration.

**ChatGPT Desktop / Codex Files:**
*   `.codex-plugin/plugin.json`: The ChatGPT plugin manifest.
*   `.mcp.json`: The ChatGPT MCP server connection configuration.

---

## 🚀 Installation

### For Google Antigravity Users
1. Clone or download this repository.
2. Move the entire folder into your workspace's `.agents/plugins/` directory (e.g., `.agents/plugins/onvidio/`) or your global `~/.gemini/config/plugins/` directory.
3. The IDE will automatically discover the plugin, load the skills, and connect to the Onvidio MCP server.

### For ChatGPT Desktop Users

The simplest way is to install it directly from the GitHub repository using the ChatGPT Desktop app:
1. Open the **Add plugin marketplace** dialog in the app.
2. Set **Source** to the URL of this repository (e.g., `git@github.com:org/repo.git`).
3. Set **Git ref** to `main`.
4. 4. Set **Sparse paths** to `/`.

*(Alternative CLI Method)*: Clone the repository locally and run:
```bash
codex plugin install /path/to/this/repository
```

---

## 🛠 Features
* Connects directly to the Onvidio API.
* Provides AI agents with the ability to dynamically design video scenes.
* Enforces strict layout and branding constraints via universal `skills`.
