# clawdbot x GChat

**Built by [Remix Partners](https://remixpartners.ai)** | Fork of [Clawdbot](https://github.com/clawdbot/clawdbot)

A personal AI assistant that lives in Google Chat. Message your AI assistant from Google Chat on any device — phone, tablet, or desktop.

---

## What It Does

Clawdbot turns Google Chat into a direct line to your own AI assistant. Instead of switching to ChatGPT or Claude in a browser, you just message your assistant in Google Chat like you would a friend.

## Features

- **Always available** — Message your AI from Google Chat on any device
- **Private** — Runs on your own machine, your conversations stay yours
- **Powerful** — Uses Claude or GPT-4 as the brain
- **Extensible** — Add tools like web browsing, file access, and more

---

## Quick Start (15-20 minutes)

### What You'll Need

- A computer (Mac, Windows, or Linux)
- A Google Cloud account (free tier works)
- An AI subscription (Anthropic Claude or OpenAI ChatGPT)
- Node.js 22 or newer ([download here](https://nodejs.org/))

---

### Step 1: Install Clawdbot

Open Terminal (Mac/Linux) or PowerShell (Windows) and run:

```bash
npm install -g clawdbot@latest
```

### Step 2: Run the Setup Wizard

```bash
clawdbot onboard --install-daemon
```

This will walk you through:
- Connecting your AI account (Anthropic or OpenAI)
- Setting up the Gateway (the control center)

### Step 3: Create a Google Chat Bot

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project (or use an existing one)
3. Search for **"Google Chat API"** and enable it
4. Go to **APIs & Services > Credentials**
5. Click **"Create Credentials" > "Service Account"**
6. Download the JSON key file

### Step 4: Configure Google Chat in Clawdbot

Create or edit `~/.clawdbot/clawdbot.json`:

```json
{
  "agent": {
    "model": "anthropic/claude-opus-4-5"
  },
  "gchat": {
    "enabled": true,
    "credentialsPath": "/path/to/your/service-account.json",
    "allowFrom": ["your-email@gmail.com"]
  }
}
```

Replace:
- `/path/to/your/service-account.json` with the actual path to your downloaded JSON file
- `your-email@gmail.com` with your Google account email

### Step 5: Start the Gateway

```bash
clawdbot gateway --port 18789 --verbose
```

### Step 6: Message Your Bot!

Open Google Chat and start a conversation with your bot. That's it — you now have a personal AI assistant in Google Chat!

---

## Troubleshooting

**Bot not responding?**
- Make sure the Gateway is running (`clawdbot gateway --verbose`)
- Check that your email is in the `allowFrom` list
- Run `clawdbot doctor` to diagnose issues

**Need help?**
- Full docs: [docs.clawd.bot](https://docs.clawd.bot)
- Original project: [github.com/clawdbot/clawdbot](https://github.com/clawdbot/clawdbot)

---

## Support

Website: [remixpartners.ai](https://remixpartners.ai)
Email: [info@remixpartners.ai](mailto:info@remixpartners.ai)

---

## Disclaimer

THIS SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AND NONINFRINGEMENT. IN NO EVENT SHALL REMIX PARTNERS OR THE ORIGINAL AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES, OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT, OR OTHERWISE, ARISING FROM, OUT OF, OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

This is a fork of [Clawdbot](https://github.com/clawdbot/clawdbot), an open-source project by Peter Steinberger and the community. This fork is provided free of charge for informational and educational purposes. Use at your own risk. We make no guarantees regarding accuracy, reliability, availability, or fitness for any particular purpose. AI model access requires separate subscriptions to Anthropic or OpenAI.

---

*Copyright 2026 [Remix Partners](https://remixpartners.ai). Original Clawdbot MIT licensed by Peter Steinberger.*
