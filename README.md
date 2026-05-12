## Table of Contents

- Overview
- Key Features
- System Architecture
- Technology Stack
- Project Structure
- Module Deep Dive
- Data Flow
- Installation & Setup
- Configuration
- API Reference
- Access Control Matrix
- Security & Compliance
- Scripts & Utilities
- Testing
- Frontend Overview
- Deployment
- Roadmap & Future Enhancements
- Contributing

---

## Overview

JARVIS is an autonomous AI daemon built in `Bun` with a TypeScript backend and React/Tailwind frontend. It uses a central server process plus desktop sidecars for cross-machine automation, screen awareness, and workflow orchestration. The repo combines:
- `Bun` runtime for server/CLI
- `TypeScript` for core app logic
- `React 19` + `Tailwind CSS 4` for UI
- `Go` for native desktop sidecar automation
- `Python` for biometric/livekit sidecar tooling

---

## Key Features

- Persistent AI daemon with always-on goal pursuit
- Multi-agent roles and authority controls
- Desktop awareness via sidecars
- Visual workflow builder and automation engine
- Voice interface + wake word support
- Multi-LLM provider integration
- Encrypted/local vault storage
- WebSocket-based dashboard + sidecar protocol

---

## System Architecture

- `Brain daemon` runs in Bun, exposing HTTP + WebSocket APIs
- `UI dashboard` served by Bun and built with React/Tailwind
- Sidecar process in Go connects over JWT-authenticated WebSocket
- Biometrics-sidecar Python helpers for additional agents and legacy mic handling
- `Vault` persistence stored in SQLite via `bun:sqlite`
- `LLM provider` connectors handled in TypeScript
- `Frontend` assets built using Bun bundler from index.html

---

## Technology Stack

### Core Runtime
- `Bun` (primary runtime)
- `TypeScript` (application language)
- `React 19` (UI)
- `Tailwind CSS 4` (styling)
- `Go` (desktop sidecar binary)
- `Python` (biometrics / livekit / legacy sidecar tooling)

### Backend / Server
- `Bun.serve()` for HTTP + WebSocket server
- `bun:sqlite` for database access
- `jose` for JWT auth
- `yaml` for config parsing
- `Bun.spawn` / `Bun.file` utilities

### Frontend / UI
- `React`
- `@xyflow/react`
- `CodeMirror` editors (`@codemirror/*`)
- `react-markdown`, `remark-gfm`, `rehype-highlight`
- `highlight.js`
- `@types/react`, `@types/react-dom`

### AI / Voice / Media
- `discord.js` integration
- `edge-tts-universal`
- `openwakeword-wasm-browser`
- `onnxruntime-web`
- `tesseract.js`
- `sharp`

### Developer Tooling
- `bun test`
- `bun build`
- `bun install`
- `TypeScript` compiler support
- Dockerfile for container deployment

---

## Project Structure

- bin — CLI launcher and helper commands
- src — main Bun/TypeScript source code
- daemon — server daemon entrypoint
- llm — LLM provider integration and tests
- vault — SQLite storage and vault persistence
- ui — frontend app
- webapp-templates — browser automation templates
- sidecar — Go native desktop automation agent
- biometrics-sidecar — Python biometrics / voice sidecar support
- scripts — setup/build helper scripts
- docs — architecture, workflows, sidecar protocol docs
- examples — sample integrations and demos
- config.example.yaml — config schema example

---

## Module Deep Dive

### daemon
- Main daemon
- HTTP dashboard routing
- WebSocket protocol for clients and sidecars

### llm
- Provider adapters
- LLM test harness
- multi-provider support for OpenAI, Anthropic, Gemini, Ollama, Groq

### vault
- SQLite-based vault persistence
- Workflow storage, memory graph, secure data
- `db:init` schema initialization

### ui
- React/Tailwind dashboard
- Workflow editor and visual automation
- Markdown rendering and editor components

### sidecar
- Cross-platform Go agent
- Win32 / X11 / macOS automation
- JWT-authenticated WebSocket RPC

### biometrics-sidecar
- Python sidecar utilities
- LiveKit voice agent
- face auth and mic bridge

---

## Data Flow

1. User interacts with dashboard in browser
2. Frontend talks to Bun daemon over HTTP/WebSocket
3. Daemon stores state in SQLite vault
4. Sidecars connect to daemon via JWT-authenticated WebSocket
5. Sidecars send screen, input, browser, and system events
6. Daemon orchestrates workflows, agents, and LLM calls
7. Responses and actions propagate back to UI and sidecars

---

## Installation & Setup

- `bun install`
- `bun run build:ui`
- `bun run src/daemon/index.ts`
- `bun run launch.ts` for managed startup
- `cd biometrics-sidecar && pip install -r requirements.txt && playwright install chromium`

Key scripts:
- `launch`
- `start`
- `dev`
- `build:ui`
- `db:init`
- `setup`
- `test`
- `setup:google`

---

## Configuration

- config.example.yaml shows auth, dashboard, provider, and sidecar options
- Use YAML config plus environment variables
- JWT authentication for dashboard and sidecars
- External provider keys for:
  - Google OAuth
  - Discord
  - ElevenLabs / Edge TTS
  - LLM services

---

## API Reference

- CLI: `jarvis start`, `jarvis stop`, `jarvis status`, `jarvis logs`, `jarvis doctor`
- HTTP dashboard endpoints from Bun daemon
- WebSocket API for frontend and sidecars
- Sidecar protocol documented in SIDECAR_PROTOCOL.md
- vault and workflow APIs exposed via internal JSON event bus

---

## Access Control Matrix

- Dashboard access protected by auth config
- Sidecar access protected by JWT
- Role-based authority scopes for agents
- Audit trail of actions and runtime enforcement
- Config defines allowed capabilities per client/sidecar

---

## Security & Compliance

- Runtime isolation in Bun
- JWT-secured WebSocket connections
- YAML config avoids storing secrets in UI bundles
- Separate encrypted SQLite files for sensitive data
- `jose` library for crypto/JWT handling
- Sidecar authentication and connection security documented in SIDECAR_AUTHENTICATION.md

---

## Scripts & Utilities

From package.json:
- `launch`
- `start`
- `dev`
- sidecar
- `mcp`
- `livekit`
- `install:sidecar`
- `copy:models`
- `prebuild:ui`
- `build:ui`
- `test`
- `db:init`
- `setup`
- `test:llm`
- examples
- `setup:google`
- `postinstall`
- `prepare`
- `prepublishOnly`

---

## Testing

- `bun test`
- `bun test src/llm/test.ts`
- `bun test src/workflows/`
- docs reference workflow and vault tests
- core testing via Bun’s test runner

---

## Frontend Overview

- `React 19`
- `Tailwind CSS 4`
- `@xyflow/react` for workflow UI
- CodeMirror-based editors
- Markdown support via `react-markdown`, `remark-gfm`, `rehype-highlight`
- Built and served from index.html using Bun’s bundler

---

## Deployment

- Primary deployment via Bun runtime
- Dockerfile available for container deployments
- Install script available in install.sh
- Managed hosting option referenced in README
- `prepublishOnly` builds UI and copies model assets

---

## Roadmap & Future Enhancements

- Mobile companion / React Native support
- Expanded smart-home integrations
- More sidecar automation platforms
- Better offline/local LLM support
- Additional workflow node types and provider connectors

---

## Contributing

- Use GitHub issues and pull requests
- `prepare` hook sets `core.hooksPath`
- Follow existing repo structure for new source, docs, and examples
- Run `bun test` and `bun run build:ui` before submitting changes

---
