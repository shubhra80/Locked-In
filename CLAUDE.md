# Locked In — CLAUDE.md

## What This Project Is
Locked In is a Gen Z SMS-based focus companion for teenagers. 
It helps teenagers complete focused work sessions through casual, 
low-pressure text conversations. No app to download. No dashboard 
to check. Just a daily text that starts a conversation.

## The Core User Flow
1. Daily text sent to the teenager at their preferred time
2. Teen replies with what they want to focus on
3. App confirms and starts a 25 minute timer
4. After 25 minutes, app sends a check-in text
5. Teen responds with how it went
6. Response is logged for future analytics
7. App closes the loop with encouragement — no lectures

## The Tone — This Is Critical
- Casual and low pressure — like a cool older sibling, not a parent
- Short sentences, minimal punctuation, lowercase where it feels natural
- Never preachy, never lecture-y, never parental
- Light humor is good — trying too hard is worse than being boring
- Gen Z adjacent but not cringe — less "no cap fr fr bussin" 
  and more just relaxed and direct
- The opening text: "bet you can't focus for 25 mins straight. 
  prove me wrong. what are we working on"

## Tech Stack
- Language: Python
- SMS: Twilio API
- AI Conversation: Claude API (claude-sonnet-4-6)
- Database: Airtable (MVP) — for logging sessions and responses
- Version Control: GitHub
- Built with: Claude Code

## MCP Servers
- Twilio MCP — for sending and receiving SMS
- Airtable MCP — for logging session data
- GitHub MCP — for version control

## Architecture Principles
- MVP first — get the text flow working before adding anything else
- Design for analytics from day one — log everything even if 
  we don't display it yet
- Every feature must be addable later without rebuilding the core
- Keep it simple enough that a non-engineer can maintain it

## MVP Scope — Build This First
- [ ] Daily scheduled text sent via Twilio
- [ ] Receive and parse teen's reply
- [ ] Send timer confirmation text
- [ ] Send 25 minute check-in text
- [ ] Receive and log end-of-session response
- [ ] Simple encouragement response to close the loop

## Phase 2 — Add Later
- Weekly pattern insights
- Streak tracking
- Adaptive AI tone based on response patterns
- Multiple users
- Parent dashboard (teen controls sharing)

## What NOT To Do
- Never require the teenager to download an app
- Never require account creation
- Never send more than 3 texts per session — keep it minimal
- Never sound like a productivity guru or life coach
- Never add a feature that breaks the simplicity of the SMS flow

## File Structure
locked-in/
├── CLAUDE.md          # This file
├── README.md          # Project description for GitHub
├── main.py            # Core application logic
├── twilio_handler.py  # All Twilio SMS functions
├── claude_handler.py  # All Claude API functions
├── scheduler.py       # Daily text scheduling logic
├── database.py        # Airtable logging functions
├── config.py          # Configuration and environment variables
├── .env               # API keys — never commit this file
├── .gitignore         # Ignore .env and other sensitive files
└── requirements.txt   # Python dependencies

## Environment Variables Needed
TWILIO_ACCOUNT_SID=
TWILIO_AUTH_TOKEN=
TWILIO_PHONE_NUMBER=
CLAUDE_API_KEY=
AIRTABLE_API_KEY=
AIRTABLE_BASE_ID=

## Session Rules for Claude Code
- Always check this CLAUDE.md at the start of every session
- Never commit .env files to GitHub
- Always maintain the casual teen tone in any SMS copy
- When in doubt, keep it simpler — complexity can always be added later
- Log everything to Airtable even if it's not being displayed yet

## The Bigger Picture
This project is being built in public as a portfolio piece. 
Each phase of the build will be documented on LinkedIn. 
The goal is to demonstrate that AI-native product development 
is a transferable skill — from consumer apps to enterprise products, 
the architecture is the same.
