# Rahi AI — Advanced Hybrid Agent (V1)

A real Android/Kotlin starter project for a personal AI assistant with:

- Online AI provider support through an OpenAI-compatible Chat Completions endpoint
- Offline fallback assistant (rule-based in V1)
- Local personal memory
- Bengali voice input using Android SpeechRecognizer
- Automatic online/offline detection
- Safe local tools: remember, recall, open a URL
- Extensible agent/tool architecture for future phone, coding, web and automation tools

## Important reality check

This V1 is intentionally honest about offline AI. It does **not** pretend that a rule-based fallback is a generative LLM. To get true generative offline chat, add a compatible on-device LLM runtime and a small quantized model appropriate for the phone's RAM, then implement the `LocalModelEngine` interface described in `models/README.md`.

The app does not get unrestricted phone control. Android permissions and user confirmation should remain in place for sensitive actions.

## Build

Open the `RahiAI` folder in a current Android Studio installation. The project uses Android Gradle Plugin 9.0.1, Kotlin 2.4.10, compileSdk 36, and Java 17.

Then sync Gradle and run the `app` configuration on an Android device.

## Configure online AI

Open **⚙ Settings** inside the app and enter:

1. API endpoint
2. API key
3. Model name

The app expects a response compatible with the common `/chat/completions` shape: `choices[0].message.content`.

### Security warning

For a personal prototype, an API key stored on-device can be acceptable, but it is not a secure production architecture. A production release should call your own backend and keep provider secrets server-side.

## Roadmap

- V1: Hybrid chat + memory + voice + safe local tools
- V2: Real on-device LLM engine
- V3: Tool registry + explicit confirmation + task planner
- V4: Firebase/cloud memory + project workspace
- V5: Controlled Android automation and coding agent
