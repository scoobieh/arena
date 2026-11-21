# ArenaAI Chat — iPhone App (v2: Agents + All Models + Dolphin)

Full Arena-style chat app for iPhone with **Agents** and **every major model family**.

## Models built in
- **OpenAI (all GPTs):** GPT-4o, GPT-4o mini, o1, o1-mini, o3-mini, GPT-4 Turbo, GPT-3.5 Turbo
- **Anthropic:** Claude 3.5 Sonnet, Claude 3 Opus, Claude 3 Haiku
- **Google:** Gemini 1.5 Pro, Gemini 1.5 Flash, Gemini 2.0 Flash
- **OpenRouter (100+ models, one key):**
  - 🐬 **Mistral Dolphin 72B — Uncensored** (`cognitivecomputations/dolphin-2.9.2-qwen2-72b`)
  - Dolphin 2.9.1 72B — Uncensored
  - Nous Hermes Mixtral — Uncensored
  - Mistral Large, Mistral 7B, Llama 3.1 405B / 70B
  - GPT-4o, Claude 3.5, Gemini 1.5 via OpenRouter
- **Free AI:** Pollinations (no key)
- **Demo:** offline canned replies

## Agents built in
Tap the **Agent** button next to the model picker:
- 🤖 General • 💻 Coder • 🔍 Researcher • ✍️ Writer • 📊 Analyst • 🎓 Tutor • 🐬 Dolphin (direct style)

Each agent injects its own system prompt into every request.

## Install on iPhone

### ✅ Method 1 — Add to Home Screen (recommended, never expires)
1. Host `index.html` + `icon.png` free at [app.netlify.com/drop](https://app.netlify.com/drop) (drag both files in)
2. Open the URL in **Safari on your iPhone**
3. **Share → Add to Home Screen → Add**
4. Open the ArenaAI icon — full-screen native-feel app

### 🔧 Method 2 — True .IPA sideload
1. Mac + Xcode → New App (SwiftUI) → replace `ContentView.swift` with `ArenaAIChatApp.swift`
2. Drag `index.html` + `icon.png` into the project → Run on iPhone
3. Archive → export `.ipa` → install with Sideloadly / AltStore / SideStore
   - Note: free Apple IDs expire in 7 days; AltStore auto-refreshes.

## Connect a real model
Tap **⚙️ Settings**:
- **OpenRouter** (recommended for Dolphin + everything): key at openrouter.ai/keys
- **OpenAI**: platform.openai.com/api-keys
- **Anthropic**: console.anthropic.com
- **Gemini**: aistudio.google.com (free tier)
- Or **Free AI** — no key at all

Keys are stored only in your browser's localStorage on your device.

## Files
| File | Purpose |
|---|---|
| `index.html` | Complete app v2 |
| `icon.png` | App icon |
| `ArenaAIChatApp.swift` | Native wrapper for IPA |
| `README.md` | This guide |
