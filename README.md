🌌 Introduction
Z.E.N.I.T.H is not just a chatbot; it is a distributed, high-performance desktop assistant architected to live on your machine and execute real-world tasks autonomously.

Powered by a local LLM brain and utilizing a high-speed Bun-powered sidecar within a Microservices framework, Z.E.N.I.T.H processes commands with zero latency. From face-authenticated system access to sending autonomous WhatsApp messages via native UI interaction, it bridges the gap between conversational AI and functional system execution.

⚡ Core Philosophy & Architecture
Speed. Security. Scalability.

Instead of building a monolithic script, Z.E.N.I.T.H is engineered as an event-driven network:

The LLM Brain: The central processing node that understands natural language intent.

The Sidecar Pattern: High-speed I/O operations and API handling are offloaded to a Bun runtime, ensuring the Python core never blocks.

Microservices Integration: Built to easily hook into your existing Kafka or Redis event streams, allowing the AI to monitor background processes or trigger complex distributed workflows.

Vision & Security: Leverages OpenCV for local face authentication before executing privileged desktop commands.

🛠️ Key Capabilities
🎙️ Voice & Text Modalities: Interact via seamless voice recognition or silent CLI text input.

👁️ Face Authentication: Secure your assistant. Z.E.N.I.T.H verifies your identity using your webcam before running sensitive modules.

💬 Autonomous WhatsApp Module: Automatically resolves contact names to numbers, invokes the Windows Desktop URI scheme, and sends messages via PyAutoGUI without manual intervention.

🧩 Extensible Capabilities: Easily drop in new Python or Java modules into the modules/ directory to expand its skill set.

🚀 Getting Started
Prerequisites
Ensure your system meets the following requirements:

Python >= 3.10

Bun (for sidecar execution)

A webcam (if using the --auth flag)

WhatsApp Desktop App installed (for the messaging module)

Installation
Bash
# Clone the repository
git clone https://github.com/yourusername/zenith-ai.git
cd zenith-ai

# Install Python dependencies
pip install -r requirements.txt

# Install Bun sidecar dependencies
cd sidecar
bun install
cd ..
Configuration
Create a contacts.json file in your modules/ directory to map names to phone numbers for the messaging module:

JSON
{
  "karthik": "+919876543210",
  "prasad": "+911234567890"
}
Usage
Z.E.N.I.T.H offers multiple boot modes depending on your environment:

Bash
# Normal mode (Face Authentication + Voice Interface)
python zenith.py

# Quick mode (Skip face authentication)
python zenith.py --no-auth

# Stealth mode (Text input only, no microphone)
python zenith.py --text

# Developer mode (Text input, no auth, verbose logging)
python zenith.py --text --no-auth --debug
🧭 Roadmap
The vision for Z.E.N.I.T.H is continually expanding. Current milestones include:

[x] Initial LLM Brain integration

[x] Local Face Authentication using OpenCV

[x] WhatsApp Desktop automation via URI & PyAutoGUI

[ ] Migrate heavy I/O operations to the Bun sidecar

[ ] Establish an Event-Driven architecture (Kafka/Redis) for background task monitoring

[ ] Advanced Micro-Expression Analyzer integration

🤝 Contributing
Contributions are welcome! Whether it's adding a new module, optimizing the Bun sidecar, or refining the intent extraction, your help makes Z.E.N.I.T.H better.

Fork the project.

Create your feature branch (git checkout -b feature/AmazingFeature).

Commit your changes (git commit -m 'Add some AmazingFeature').

Push to the branch (`git push origin feature/AmazingFeature

Plaintext
╔════════════════════════════════════════════════════════════════════╗
║                      Z.E.N.I.T.H  AI  DAEMON                       ║
║    Zero latency Engineered Network for Intuitive Task Handling     ║
║                                                                    ║
║                  Autonomous AI Desktop Assistant                   ║
║  Face-Auth | LLM | Bun | Microservices | Sidecar-Driven | Modular  ║
╚════════════════════════════════════════════════════════════════════╝
Your autonomous, multimodal AI desktop daemon.

🌌 The Vision
Z.E.N.I.T.H is not just a chatbot; it is a highly scalable, autonomous agentic network designed to live directly on your machine. Engineered with a zero-latency philosophy, it bridges the gap between natural language processing and actual native system execution.

Whether you are communicating via voice, requesting complex microservice orchestrations, or delegating repetitive tasks, ZENITH operates with full autonomy, secured by local facial authentication.

Core Philosophy
True Autonomy: ZENITH doesn't just answer questions; it executes actions natively (like controlling local desktop apps, managing files, or sending messages) via a highly modular capability system.

Performance First: The core LLM "Brain" handles reasoning, while heavy I/O operations and high-speed scripts are offloaded to Bun-powered sidecars to guarantee zero latency.

Distributed Architecture: Built on a microservices foundation, allowing seamless integration with message brokers (like Kafka), in-memory stores (Redis), and containerized deployments (Docker/Kubernetes).

Privacy & Security: Features local Face Authentication via OpenCV. If it doesn't recognize you, it doesn't execute.

⚡ Technical Architecture
ZENITH breaks away from monolithic assistant designs. It utilizes a Sidecar Pattern to isolate the cognitive load from the execution load.

The Brain (Python): Handles speech-to-text, LLM context management, intent extraction, and face authentication.

The Nervous System (Microservices): Event-driven communication channels routing intents to the correct modules.

The Hands (Bun & Node.js Sidecars): High-speed execution engines that interact with the OS, APIs, web scraping, and third-party apps (e.g., WhatsApp Desktop URI routing).

🚀 Getting Started
Prerequisites
To run the ZENITH Daemon, your environment must be equipped with the following:

Python >= 3.10

Bun (for executing JavaScript/TypeScript sidecar modules)

A webcam (for Face Authentication)

Optional but recommended: Docker & Kubernetes for deploying isolated service modules.

Installation
Bash
# 1. Clone the repository
git clone https://github.com/yourusername/zenith-ai.git
cd zenith-ai

# 2. Install Python dependencies for the core Daemon
pip install -r requirements.txt

# 3. Install dependencies for the Bun sidecars
cd sidecars && bun install && cd ..
Usage Modes
ZENITH can be launched in multiple states depending on your current environment and privacy needs.

Bash
# Standard Mode: Boots the daemon with Face Auth and Voice Listeners active
python zenith.py

# Dev Mode: Skips face authentication for rapid testing
python zenith.py --no-auth

# Silent Mode: Accepts text input only (disables microphone and wakeword)
python zenith.py --text

# Headless Dev Mode: Text only, no authentication
python zenith.py --text --no-auth
🧠 Module Ecosystem (Capabilities)
ZENITH's capabilities are highly modular. You can drop new logic into the network without rewriting the core.

Current active modules include:

System Operations: Launching apps, managing windows, hardware metrics.

Communication: Autonomous WhatsApp messaging via local desktop URI integration.

DevOps: Spinning up Docker containers, checking Kubernetes cluster health.

Vision: AI Micro-Expression analysis and user recognition.

🛠 Contributing & Expanding
ZENITH is designed to grow. Because it utilizes an event-driven microservice architecture, you can write a module in Java, Python, or Go, containerize it, and have ZENITH's event bus trigger it.

To add a new capability:

Define the intent schema in the Brain.

Create the execution logic in a Bun sidecar or a Python module.

Register the capability in the Daemon's CAPABILITIES dictionary.

## 👨‍💻 Built By

Architected and engineered by **Team Zenith**:
* **nnssprasad** 
* **Manikanta**
