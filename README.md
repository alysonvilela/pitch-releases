<p align="center">
  <a href="https://pitch.seusoc.io/">
    <img src="assets/app-icon.png" alt="Pitch" width="96" />
  </a>
</p>

<p align="center">
  <img src="assets/pitch.svg" alt="" width="48" />
</p>

<h1 align="center">Pitch</h1>

<p align="center">
  Talk instead of typing. Meetings turn into notes.
</p>

<p align="center">
  <a href="https://pitch.seusoc.io/"><strong>pitch.seusoc.io</strong></a>
</p>

<p align="center">
  <a href="https://github.com/alysonvilela/pitch-releases/releases/latest"><img alt="Latest release" src="https://img.shields.io/github/v/release/alysonvilela/pitch-releases?label=latest%20release" /></a>
  <a href="https://github.com/alysonvilela/pitch-releases/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/alysonvilela/pitch-releases/total?label=downloads" /></a>
  <a href="#macos"><img alt="macOS Apple Silicon" src="https://img.shields.io/badge/macOS-Apple%20Silicon-111111" /></a>
  <a href="#windows"><img alt="Windows 10 and 11, x64" src="https://img.shields.io/badge/Windows-10%20%26%2011%2C%20x64-111111" /></a>
</p>

Pitch turns your voice into text in any app, and a meeting into a transcript and a note. Transcription runs on your computer and works offline. It's free for personal use, on macOS and Windows.

The recommended voice model covers Portuguese and English and transcribes without internet, on your own computer.

This repository publishes the installers and the update feed. The product site is [pitch.seusoc.io](https://pitch.seusoc.io/).

## Features

Pitch lives in the menu bar and works in any app, without switching windows.

- **Dictation.** Press ⌘E and talk. The text lands in whatever field has focus: Slack, Gmail, Notion, Linear, Docs, Meet, Zoom, Figma, GitHub, a calendar, a sheet, or slides. On Windows, use Ctrl instead of ⌘, so the shortcut is Ctrl+E.
- **Meeting notes, without adding anyone to the call.** Press ⇧⌘E (Ctrl+Shift+E on Windows). Pitch records your microphone and the system audio, so it hears both sides of Meet, Zoom, Teams, or any other app. When the call ends, you get the transcript and a note with decisions and next steps.
- **Your vocabulary.** Names, acronyms, and technical terms can come out spelled the way you want.
- **History you control.** Play a recording back, transcribe it again, or delete recordings one at a time or in bulk.
- **Optional AI.** Loose speech can become an email, a message, or a prompt. Use Ollama or LM Studio on your computer, or OpenAI, Anthropic, or OpenRouter with your own key. Or leave AI off.
- **Your own tools**, in the current release:
  - Settings › Integrations connects Claude Code, Claude Desktop, Cursor, VS Code, Codex, or OpenCode to your notes in one click. Other apps that run a local MCP server can copy the setup. What an AI app changes stays in the note, and you can restore it with one click.
  - Webhooks send note events (created, updated, or moved, plus transcriptions and AI-written notes) to the URLs and folders you pick. Pitch retries a failed delivery, keeps a log, and lets you resend one.
  - Drop an audio or video file on the menu bar icon, or choose **Transcrever arquivo…** (transcribe a file) in its menu. Pitch transcribes it on your computer.
- **Hidden from screen sharing.** Pitch doesn't show up in screenshots, recordings, or calls.

Personal use is free. That includes local dictation and notes, all local speech models, and your own AI keys or local models. Teams and Enterprise are coming soon.

## Download

The current release is **1.6.4**, published November 25, 2026. These links point at the assets on the [latest release](https://github.com/alysonvilela/pitch-releases/releases/latest). Older builds are on the [releases page](https://github.com/alysonvilela/pitch-releases/releases).

The installers are not code-signed yet, so macOS and Windows warn you. The steps under each system are how to get past that.

### macOS

Apple Silicon (M1 or newer). [Download Pitch_1.6.4_aarch64.dmg](https://github.com/alysonvilela/pitch-releases/releases/latest/download/Pitch_1.6.4_aarch64.dmg) · 20.7 MB

1. Open the disk image and drag **Pitch** into your Applications folder.
2. Pitch isn't notarized by Apple yet. In Terminal, clear the quarantine flag:

   ```sh
   xattr -dr com.apple.quarantine /Applications/Pitch.app
   ```

   If macOS says the app is damaged or can't be opened, that command is the fix. You can also allow it in **System Settings → Privacy & Security → Open Anyway**.
3. Open Pitch from Applications.

The `.app.tar.gz` file on the release is the package the in-app updater downloads. For a first install, use the `.dmg`.

### Windows

Windows 10 and 11, x64. [Download Pitch_1.6.4_x64-setup.exe](https://github.com/alysonvilela/pitch-releases/releases/latest/download/Pitch_1.6.4_x64-setup.exe) · 22.2 MB

1. Run `Pitch_1.6.4_x64-setup.exe`.
2. The installer isn't signed yet. If SmartScreen says "Windows protected your PC", click **More info**, then **Run anyway**.

### Check the download

Every release publishes a [SHA256SUMS](https://github.com/alysonvilela/pitch-releases/releases/latest/download/SHA256SUMS) file for the `.dmg` and the `.exe`. Download it into the same folder as the installer and run:

```sh
shasum -a 256 -c SHA256SUMS
```

Your file should show up as OK.

On Windows, PowerShell can compute the SHA-256. Compare it with the line for that file in `SHA256SUMS`:

```powershell
Get-FileHash .\Pitch_1.6.4_x64-setup.exe -Algorithm SHA256
```

## Quick start

Install, open Pitch, and follow the guided setup. It takes about a minute. You can change any of these later in Settings.

1. **Permissions.** Microphone, so Pitch can hear you. Accessibility, so it can type into the app in focus. Those are the only two it asks for. Your voice stays on your computer.
2. **Voice model.** Pitch downloads a model. The recommended one covers Portuguese and English and transcribes without internet, on your own computer.
3. **Shortcuts.** ⌘E dictates into the field in focus. ⇧⌘E records the meeting into a note. On Windows, use Ctrl instead of ⌘.
4. **Providers.** Optional. Ollama or LM Studio on your computer, or OpenAI, Anthropic, or OpenRouter in the cloud. Or none.
5. **Done.** Dictate into an app, or record a meeting.

## Privacy

Transcription runs on your computer and works offline. Your audio never leaves the machine. Your mic and the call audio become a note without touching a server.

AI for notes is optional. A local model stays on the computer. A cloud provider uses the API key you bring.

Pitch can send usage statistics. With that on, it sends counts and times (dictations, words, duration), the errors that happen, which apps you dictate into, and your state and country. Those are tagged with a random installation ID, linked to the name and email you enter the first time you open the app. Audio, transcripts, notes, and your keys are never sent, and your IP address isn't stored. Turn it off in **Settings › General › Send usage statistics** (Configurações › Geral › Enviar estatísticas de uso while the app is in Portuguese). The [privacy policy](https://pitch.seusoc.io/en/privacidade) has the rest.

## FAQ

**Does my voice go to the cloud?**

Not unless you want it to. Transcription runs on a voice model downloaded to your computer and works offline. AI for notes is optional. It can run locally with Ollama or LM Studio, or with a cloud provider you pick, using your own key.

**Does Pitch collect what I say?**

It collects numbers and errors, not what you say or write. See [Privacy](#privacy) for the list and how to turn statistics off.

**Which systems does it run on?**

The current version runs on macOS with Apple Silicon (M1 or newer) and on Windows 10 and 11, x64.

**Does the recommended model cover Portuguese?**

Yes. The recommended voice model covers Portuguese and English and transcribes without internet, on your own computer. You can also set the app to Portuguese, English, or your system language in Settings.

**Does Pitch update itself?**

Yes. Since version 1.3.0, Pitch lets you know in the app when a new version is out and installs the update when you restart. You can see the current version and check for an update in Settings → General → Application.

**macOS says the app is damaged. What now?**

Pitch isn't notarized by Apple yet. Move the app to Applications and run `xattr -dr com.apple.quarantine /Applications/Pitch.app` in Terminal, or allow it in System Settings → Privacy & Security → Open Anyway. The [macOS](#macos) section has the steps in order.

**Windows showed "Windows protected your PC".**

The installer isn't signed yet. Click **More info**, then **Run anyway**.

**Do I need a bot in the meeting?**

No. Pitch records system audio along with your microphone, so it hears Meet, Zoom, Teams, or any other app with no one extra in the call.

**How do I verify the download?**

Download [SHA256SUMS](https://github.com/alysonvilela/pitch-releases/releases/latest/download/SHA256SUMS) into the same folder, run `shasum -a 256 -c SHA256SUMS`, and check that your file shows as OK.

**Is Pitch free?**

Pitch is free for personal use. Teams and Enterprise are coming soon.

## Feedback

Questions, ideas, and problems go to the [feedback board](https://pitch.userjot.com/).

Release notes are in English on [GitHub Releases](https://github.com/alysonvilela/pitch-releases/releases) and on the site under [What's new](https://pitch.seusoc.io/en/novidades).

[pitch.seusoc.io](https://pitch.seusoc.io/) · [Privacy policy](https://pitch.seusoc.io/en/privacidade) · [Terms of use](https://pitch.seusoc.io/en/termos)
