<img width="2496" height="1172" alt="Workflow" src="https://github.com/user-attachments/assets/b21c53a1-8732-4f90-8462-a730cd0ab5d4" />



> ### 🚀 *Send code. Get clarity. Automatically.*
> An intelligent n8n automation that watches your Gmail for code-related emails, runs **parallel AI analysis** using NVIDIA Nemotron LLM, and delivers a structured code summary + inline comments back to your inbox — **hands-free.**

---

## 🌟 What Is This?

**CodeMail AI** is a no-code / low-code workflow built on **n8n** that transforms how you review and understand code. Simply email yourself (or someone else) a snippet of Python code — the workflow automatically:

1. 📥 **Detects** the email via Gmail trigger
2. ⚡ **Splits** into two parallel AI agents
3. 💬 **Agent 1** generates inline comments for every line
4. 📝 **Agent 2** writes a plain-English summary
5. 🔀 **Merges** both outputs into one clean report
6. 📤 **Emails** the full analysis back to you

---

## 🎬 Workflow Architecture

```

<img width="1272" height="1066" alt="Screenshot 2026-06-21 at 12 46 17 AM" src="https://github.com/user-attachments/assets/278369d0-f07f-40b6-b1d3-00206c654364" />

```

---

## ✨ Features at a Glance

<table>
<tr>
<td width="50%">

### 🤖 AI-Powered Analysis
- Parallel LLM processing for speed
- NVIDIA Nemotron — state-of-the-art model
- Expert-level code understanding
- Context-aware comment generation

</td>
<td width="50%">

### 📬 Gmail Native
- Automatic email polling every minute
- Fully automated — zero manual steps
- Sends report directly to your inbox
- Works with any Gmail account

</td>
</tr>
<tr>
<td width="50%">

### ⚡ Parallel Processing
- Comments & summary run simultaneously
- Smart merge via n8n Aggregate node
- Fast turnaround on code analysis
- Edit Fields for clean formatting

</td>
<td width="50%">

### 🔌 Extensible
- Built on open n8n platform
- Easy to add Slack/Discord output
- Swap any LLM model
- Add GitHub/Jira integrations

</td>
</tr>
</table>

---

## 🛠️ Tech Stack

| Layer | Technology | Role |
|-------|-----------|------|
| 🔄 Orchestration | [n8n](https://n8n.io) | Workflow automation engine |
| 🧠 LLM | [NVIDIA Nemotron](https://build.nvidia.com/nvidia/llama-3_1-nemotron-70b-instruct) | Code analysis & generation |
| 🔗 AI Framework | LangChain (via n8n) | LLM chaining & prompt management |
| 📧 Communication | Gmail API (OAuth2) | Trigger & delivery |

---

## 🤖 AI Agents & Prompts

### 💬 Comment Agent
```
System: You are a helpful assistant who knows how to write Python code.
        You can help understand code by adding comments to it.

Task:   Given the code below, generate comments for each line so the 
        reader understands what every line does. 
        ⚠️ Do NOT modify existing code — only add comments.
```

### 📝 Summary Agent
```
System: You are an expert in Python with the ability to summarize 
        code in simple language, covering all important details.

Task:   Given the code below, generate a summary in very simple 
        language. Cover all important details so the reader 
        understands the code at a quick glance.
```

---

## 🚀 Getting Started

### Prerequisites

- ✅ **n8n** — self-hosted or [cloud](https://app.n8n.cloud/)
- ✅ **Gmail account** with OAuth2 credentials configured
- ✅ **NVIDIA API key** — get one at [build.nvidia.com](https://build.nvidia.com)
- ✅ **n8n LangChain nodes** — `@n8n/n8n-nodes-langchain`

---

### ⚙️ Installation

#### Step 1 — Clone this repo

```bash
git clone https://github.com/YOUR_USERNAME/codemail-ai.git
cd codemail-ai
```

#### Step 2 — Import the workflow

Open your n8n dashboard and navigate to:

```
Workflows → ⋮ Menu → Import from File → Select LLM_Workflow.json
```

#### Step 3 — Configure credentials

| Node | Credential Type | What to Add |
|------|----------------|-------------|
| `Gmail Trigger` | Gmail OAuth2 | Connect your Gmail account |
| `Comment` | NVIDIA Nemotron | Add your NVIDIA API key |
| `Code_Summary2` | NVIDIA Nemotron | Add your NVIDIA API key |
| `Basic LLM Chain` | NVIDIA Nemotron | Add your NVIDIA API key |
| `Send a message` | Gmail OAuth2 | Same Gmail account |

#### Step 4 — Activate & Test

```
1. Toggle the workflow to Active ✅
2. Send an email to your Gmail with Python code in the body
3. Wait ~1 minute for the trigger to fire
4. Check your inbox for the AI-generated analysis! 🎉
```

---

## 📋 Usage Example

**You send this email:**

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

print(fibonacci(10))
```

**You receive this back:**

```
╔══════════════════════════════════════════╗
║           📝 CODE SUMMARY                ║
╠══════════════════════════════════════════╣
║  This code defines a recursive function  ║
║  that calculates the nth Fibonacci       ║
║  number. Base cases are 0 and 1. The     ║
║  function prints the 10th value → 55.    ║
╚══════════════════════════════════════════╝

💬 CODE WITH INLINE COMMENTS:

def fibonacci(n):                        # Define recursive function
    if n <= 1:                           # Base case: 0 or 1
        return n                         # Return n directly
    return fibonacci(n-1) + fibonacci(n-2)  # Sum of previous two
print(fibonacci(10))                     # Output: 55
```

---

## 📁 Repository Structure

```
codemail-ai/
│
├── 📄 LLM_Workflow.json      # n8n workflow — import this
└── 📖 README.md              # You are here!
```

---

## 🗺️ Roadmap

- [x] ✅ Python code commenting via LLM
- [x] ✅ Plain-English code summarization
- [x] ✅ Parallel AI processing
- [x] ✅ Gmail trigger & delivery
- [ ] 🔲 Support for JavaScript, Java, C++
- [ ] 🔲 GitHub PR / commit integration
- [ ] 🔲 Slack / Discord delivery option
- [ ] 🔲 Code quality scoring & bug detection
- [ ] 🔲 Web dashboard for analysis history

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

```bash
git checkout -b feature/amazing-feature
git commit -m '✨ Add amazing feature'
git push origin feature/amazing-feature
# Open a Pull Request 🎉
```

---

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for more information.

---

<div align="center">

**Made with ❤️ using n8n + NVIDIA Nemotron**

*If this helped you, drop a ⭐ — it means a lot!*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:06b6d4,100:6366f1&height=100&section=footer" width="100%"/>

</div>
