# ResumeAI
# ResumeAI
# 📋 ResumeAI - Smart Resume Reviewer
[ResumeAI](https://resumeaireviewer.netlify.app/)
> An AI-powered, single-file resume analysis tool built with **vanilla HTML/CSS/JS** and the **Groq API** — delivering instant, expert-level resume feedback with ATS scoring, bullet rewrites, keyword suggestions, and a polished dark-mode chat UI.

---

## 📌 Overview

ResumeAI acts as your personal AI career coach. Upload your resume in PDF, DOCX, TXT, or Markdown format, choose your focus areas, and get detailed, structured feedback — scored across 5 key dimensions — in seconds. Powered by ultra-fast **Groq LLM inference**, responses feel near-instant compared to traditional AI APIs.

No backend. No build tools. No dependencies to install. Just one `index.html` file.

---

## ✨ Features

- 📄 **Multi-format Resume Upload** — Supports PDF, DOCX, DOC, TXT, and Markdown files
- 🤖 **AI-Powered Review** — Deep analysis powered by Groq's hosted LLMs (Llama, Mixtral, Gemma)
- 📊 **5-Dimension Scoring** — Overall, ATS Compatibility, Impact, Format, and Keyword scores (each out of 100)
- 🎯 **Customizable Focus Areas** — Toggle between Overall Assessment, ATS Compatibility, Impact & Metrics, Keyword Optimization, and Bullet Rewrites
- ✍️ **Bullet Point Rewrites** — AI rewrites weak bullets with strong action verbs and quantifiable metrics
- 🔍 **ATS Keyword Gap Analysis** — Identifies missing keywords that recruiters and ATS systems look for
- 💌 **Cover Letter Opener** — Generates a tailored cover letter opening from your resume
- 🚩 **Red Flag Detection** — Highlights issues that immediately turn off recruiters
- ⚡ **Quick Action Buttons** — One-click prompts for the most common review tasks
- 🧠 **Persistent Chat History** — Multi-turn conversation with full resume context maintained
- 🌑 **Premium Dark UI** — Elegant dark theme with gold accents, noise texture, and smooth animations
- 🔄 **Model Switcher** — Choose between Llama 3.3 70B, Llama 3.1 8B, Mixtral 8×7B, or Gemma 2 9B

---

## 🖥️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Structure** | HTML5 (single-file) |
| **Styling** | CSS3 with custom design tokens, animations |
| **Logic** | Vanilla JavaScript (ES2020+) |
| **AI Backend** | [Groq API](https://console.groq.com) (OpenAI-compatible) |
| **PDF Parsing** | [PDF.js 3.11](https://cdnjs.cloudflare.com/ajax/libs/pdf.js/) |
| **DOCX Parsing** | [Mammoth.js 1.6](https://cdnjs.cloudflare.com/ajax/libs/mammoth/) |
| **Fonts** | Cormorant Garamond, Outfit, JetBrains Mono (Google Fonts) |

---

## 🤖 Supported AI Models

| Model | Speed | Quality | Best For |
|-------|-------|---------|---------|
| `llama-3.3-70b-versatile` | Fast | ⭐⭐⭐⭐⭐ | Full reviews, deep analysis |
| `llama-3.1-8b-instant` | Fastest | ⭐⭐⭐ | Quick questions |
| `mixtral-8x7b-32768` | Fast | ⭐⭐⭐⭐ | Long context, detailed feedback |
| `gemma2-9b-it` | Fast | ⭐⭐⭐ | Concise, structured responses |

---

## 🚀 Getting Started

### 1. Get a Free Groq API Key

- Visit [console.groq.com](https://console.groq.com)
- Sign up for a free account
- Generate an API key

### 2. Add Your API Key

Open `index.html` and find the configuration section near the bottom:

```javascript
// ⚙️  DEVELOPER CONFIGURATION
// Replace with your actual Groq API key.
const GROQ_API_KEY = 'YOUR_GROQ_API_KEY_HERE';
```

Replace `YOUR_GROQ_API_KEY_HERE` with your actual key.

### 3. Open in Browser

No server or installation needed — just open the file directly:

```bash
# Option A: open directly
open index.html

# Option B: serve locally (recommended for PDF parsing)
npx serve .
# or
python3 -m http.server 8080
```

> ⚠️ **Note:** PDF parsing via PDF.js works best when served over HTTP rather than opened as a local `file://` URL. Use `npx serve` or any local server for full PDF support.

---

## 🧭 How to Use

```
1. Upload Resume    →  Drag & drop or click the upload zone (PDF / DOCX / TXT / MD)
2. Choose Focus     →  Toggle the checkboxes: ATS, Impact, Keywords, Rewrites
3. Full Review      →  Click ⚡ Full Review for a comprehensive analysis
4. Ask Anything     →  Use quick-action buttons or type your own question
5. Iterate          →  Chat naturally — context is preserved across all turns
```

### Quick Action Prompts

| Button | What It Does |
|--------|-------------|
| 📊 Full Review with Scores | Complete analysis with all 5 dimension scores |
| ✍️ Rewrite Weak Bullets | Rewrites your weakest bullet points with metrics |
| 🤖 ATS Compatibility Check | Flags missing keywords and ATS formatting issues |
| 🚀 Top 5 Improvements | Prioritized action list for maximum impact |
| 🎯 Improve Summary | Enhances your resume summary/objective section |
| 💌 Cover Letter Opener | Generates a personalized cover letter intro |
| 🔍 Best Matching Roles | Identifies job titles you're most qualified for |

---

## 📊 Score System

After a full review, a live score bar appears at the top of the chat:

| Score | Range | Meaning |
|-------|-------|---------|
| 🟢 Excellent | 80–100 | Strong — minor polish needed |
| 🔵 Good | 65–79 | Solid — a few key improvements needed |
| 🟡 Fair | 45–64 | Needs work — targeted fixes required |
| 🔴 Poor | 0–44 | Significant revision recommended |

Scores are parsed automatically from AI responses and displayed as color-coded pills.

---

## 📁 Project Structure

```
index.html        ← Entire application (HTML + CSS + JS in one file)
```

That's it. One file, zero dependencies to install.

---

## ⚠️ Security Notice

> The Groq API key is embedded directly in the HTML source code. **Do not commit your real API key to a public repository.**

Recommended approaches:
- Use a `.env` file + build step to inject the key at build time
- Proxy API calls through a lightweight backend
- Use Groq's free tier and rotate keys as needed
- Add the file to `.gitignore` if the key is hardcoded locally

---

## 🎨 UI Design Highlights

- **Dark theme** with deep navy/charcoal surfaces (`#080c10` base)
- **Gold accent system** (`#c9a84c`) for CTAs, highlights, and branding
- **Noise texture overlay** via inline SVG for premium depth
- **Radial gradient halos** for subtle atmospheric lighting
- **Animated empty state** with floating glyph and step indicators
- **Smooth message animations** with cubic-bezier entrance curves
- **Typing indicator** with bouncing gold dots
- **Responsive sidebar** with sticky upload, options, and model switcher

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Make your changes to `index.html`
4. Test across browsers (Chrome, Firefox, Safari)
5. Open a Pull Request with a description of your changes

Ideas for contributions: mobile responsive layout, export chat as PDF, dark/light theme toggle, streaming response support.

---

---

## 🙏 Acknowledgements

- [Groq](https://groq.com) — Ultra-fast LLM inference API
- [PDF.js](https://mozilla.github.io/pdf.js/) by Mozilla — In-browser PDF parsing
- [Mammoth.js](https://github.com/mwilliamson/mammoth.js) — DOCX to text conversion
- [Google Fonts](https://fonts.google.com) — Cormorant Garamond, Outfit, JetBrains Mono

---

<p align="center">Built with ❤️ to help professionals land their dream jobs</p>
