# GOAT 🐐
### GitHub Actions Orchestration Tool

<div align="center">

![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Shell](https://img.shields.io/badge/Shell_Script-121011?style=for-the-badge&logo=gnu-bash&logoColor=white)
![Nuclei](https://img.shields.io/badge/Nuclei-00C851?style=for-the-badge&logo=security&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)

[![Stars](https://img.shields.io/github/stars/the5orcerer/git-auto.svg?style=social&label=Star)](https://github.com/the5orcerer/git-auto)
[![Forks](https://img.shields.io/github/forks/the5orcerer/git-auto.svg?style=social&label=Fork)](https://github.com/the5orcerer/git-auto/fork)

</div>

---

## 🎯 The Problem

Heavy scanning is part of every bug bounty hunter's workflow—whether it's subdomain enumeration, live host filtering, or full automation pipelines. But let's face it:

- 💻 Running massive scans on your personal machine eats up CPU, RAM, and bandwidth
- 🌐 In Bangladesh (and many other regions), network lag and instability make it worse  
- ⚡ Keeping your machine powered for hours means you often end up paying more for electricity than you earn from the bounty itself

Of course, you could rent a VPS or RDP. But:
- 💰 Even a moderate VPS costs money
- 💳 Payments often require international cards or services that aren't always available

So, what's the fix? You can't just stop hunting.  
That's why **GOAT** exists—your game-changer.

---

## 🚀 What is GOAT?

GOAT lets you offload heavy scans to **GitHub Actions** instead of burning your system resources.  
With GitHub Actions, you get **up to 6 hours of runtime per workflow**, and GOAT makes it simple to chain your favorite recon tools into fully automated pipelines.

### 🛠️ Currently Integrated Tools

| Tool | Purpose | Status |
|------|---------|--------|
| 🔍 **[subfinder](https://github.com/projectdiscovery/subfinder)** | Subdomain enumeration | ✅ Ready |
| 🌐 **[httpx](https://github.com/projectdiscovery/httpx)** | HTTP probing | ✅ Ready |
| 🎯 **[nuclei](https://github.com/projectdiscovery/nuclei)** | Vulnerability scanning | ✅ Ready |
| 📱 **[notify](https://github.com/projectdiscovery/notify)** | Telegram notifications | ✅ Ready |

Everything is customizable—you decide what to run, how to run it, and GOAT delivers results straight to your Telegram.

---

## 📦 Installation

### Step 1: Fork & Star ⭐
1. **Fork this repository** (drop a ⭐ if you like this poor hacker's project)

### Step 2: Telegram Setup 📱
2. **Create a Telegram bot** and grab:
   - `API Key`
   - Your personal `Chat ID`

### Step 3: GitHub Secrets 🔑
3. In your forked repo, go to:  
   ```
   Settings → Secrets → Actions → New repository secret
   ```
   Add the following secrets:
   ```
   TELEGRAM_API_KEY
   TELEGRAM_CHAT_ID
   ```

### Step 4: Personal Access Token 🗝️
4. From GitHub `Settings → Developer settings`, generate a **Personal Access Token** (repo scope)
   - Classic or fine-grained tokens both work

### Step 5: Local Setup 💻
5. Clone the repo to your machine and set the token:
   ```bash
   export GITHUB_TOKEN=xxxxxxxx
   ```
   Or edit it inside the goat file directly.

### Step 6: Global Access 🌍
6. For global usage, move the binary to:
   ```bash
   /usr/local/bin
   # or
   $HOME/.local/bin
   ```

---

## 🎮 Usage

### 🔧 Run a Single Tool
```bash
goat -f wildcards.txt -c 'subfinder -nW -all -t100'
```

### ⛓️ Chain Multiple Tools
```bash
goat -f targets.txt -c 'httpx | nuclei -t ~/nuclei-templates/http/ -es info -c 10000 -bs 500'
```

📱 Results will be sent to your Telegram automatically.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🏗️ **Resource Offloading** | Move scans from your system to GitHub's infrastructure |
| ⚡ **Cost Effective** | Save electricity costs and prevent system overload |
| ⏰ **Extended Runtime** | Run any chain of tools for up to 6 hours per workflow |
| 🔄 **Parallel Processing** | Split files or launch multiple scans in parallel |
| 📱 **Instant Notifications** | Telegram notifications with results for easy access |

---

## ⚠️ Notes & Warnings

> [!WARNING]
> - Running too many heavy scans may trigger GitHub to disable or delete your repo
> - For long-term stability, use a **private repository**
> - Public repos can also work, but **at your own risk**

---

## 🤔 Why GOAT?

<div align="center">

### Because sometimes the best VPS...
### is the one you don't pay for. 💸

</div>

---

## 🤝 Contributing

We welcome contributions! Feel free to:
- 🐛 Report bugs
- 💡 Suggest new features  
- 🔧 Submit pull requests
- 📚 Improve documentation

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

<div align="center">

**Made with ❤️ by bug bounty hunters, for bug bounty hunters**

If this tool helped you land a bounty, consider [buying me a coffee](https://buymeacoffee.com/the5orcerer) ☕

</div>