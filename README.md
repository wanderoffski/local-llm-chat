# Local LLM Chat

**Your Mac does the thinking. Your phone just talks.**

A private Android client for the model already running on your computer. No cloud. No account. No subscription. No one in the middle.

Point it at LM Studio on your Wi-Fi. Chat like the model is in your pocket.

This is not an official LM Studio app. It is a client that speaks to the local server you already run.

## Download

**[Local LLM Chat 0.0.3 APK](https://github.com/wanderoffski/local-llm-chat/releases/download/v0.0.3/Local-LLM-Chat-0.0.3.apk)**

Sideload it. Android will ask you to allow installs from the browser or Files. This is an early build for people who already run a local model.

## What it does

- Talks to LM Studio on your local network
- Streams replies as they generate
- Loads a model on the Mac from the phone
- Remembers the last server, so the second launch is just the chat
- Keeps history on the device
- Tells you what is actually wrong when it fails: Mac asleep, wrong Wi-Fi, server stopped, model not loaded

## What it does not do

- No OpenRouter
- No on-device model
- No account
- No analytics
- No ads

The model stays on hardware you control. The app is only the screen.

## Setup

1. On the computer, open LM Studio.
2. Load a model, or turn on Just in Time Model Loading.
3. Developer tab → start the server.
4. Server settings → **Serve on Local Network**.
5. Turn on **Enable CORS** if you also use a browser client.
6. Same Wi-Fi on the phone. Guest networks will not work.
7. In the app, enter the Mac’s IP. Port defaults to `1234`.

Test in the phone browser first: `http://YOUR-MAC-IP:1234/api/v1/models` should return JSON.

If the Mac firewall asks, allow incoming connections for LM Studio.

## Away from home

Install [Tailscale](https://tailscale.com) on both devices. Save the Mac’s `100.x` address as a second server. Do not port-forward 1234.

## Privacy

Chats, the server address, and settings stay on the phone. Messages go only to the address you typed. The developer never sees them.

No account. No analytics. No advertising ID. No crash reports sent home.

## Build

Open the project in Android Studio, or from the project folder:

```bash
./gradlew assembleDebug
```

The APK is `app/build/outputs/apk/debug/app-debug.apk`.

Source for the Android project is not in this repo yet. This repository ships the 0.0.3 APK and the notes above.

## Tip jar

If this replaced a chatbot subscription, the coffee fund is open. Your GPU is warm. My mug is not.

## License

MIT
