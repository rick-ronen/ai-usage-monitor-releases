# AI Usage Monitor

A small Windows widget that shows how much of your **Claude Code** and **Codex** usage limits you've used this week, and how much you can use **today** so the week lasts until your limit resets.

This repository holds the installers, release notes and privacy policy. It contains no source code.

![Compact bar](images/compact.png)

## What it shows

- **Weekly usage** and the time left until your limit resets.
- **Today's budget:** how much of the week you can use today, and how much of it you've used.
- **Claude's 5-hour session** usage, with an orange chip on the compact bar when it gets high.
- **Daily goal alerts:** set your own daily goal per tool. When you reach it, the app tells you once that day: a flashing bell on the compact bar, a Windows notification and, if you want, a sound.
- Made for people who use Codex and Claude Code. It shows coding-tool limits, not chat limits.
- ChatGPT chat usage isn't shown. OpenAI doesn't offer a way to read it, so the app can't.
- Claude chat (claude.ai and the Claude apps) shares the same limits as Claude Code, so your Claude numbers already include your chats.
- **History:** what you used each day against that day's budget, and any checks that failed, with the reason.

| Dashboard | History |
| --- | --- |
| ![Dashboard](images/dashboard.png) | ![History](images/history.png) |

## Download

Get the latest version from the **[Releases page](https://github.com/rick-ronen/ai-usage-monitor-releases/releases/latest)**. Each release has:

| File | For |
| --- | --- |
| `AIUsageMonitor-Setup-X.Y.Z.exe` | Most people: installs for your Windows account only, no admin rights needed. |
| `AIUsageMonitor-WorkLaptop-X.Y.Z.zip` | PCs where an administrator installs software. Installs for all users in Program Files; the steps are in `WORK-LAPTOP-INSTALL.md` inside the ZIP. |
| `SHA256SUMS.txt` | SHA-256 checksums of both files. |

## Troubleshooting

- If Windows says 'This program does not support the version of Windows', open the Setup.exe from File Explorer instead of the browser, or turn off compatibility mode for your browser.

## System requirements

- Windows 10 (version 2004 or later) or Windows 11, 64-bit (x64).
- At least one of these, installed and signed in on the same Windows account:
  - **Claude Code**
  - **Codex** (the Codex app or the Codex CLI)
- Nothing else: .NET and the Windows App SDK are included.

The app reads usage from these coding tools only, not from the Claude or ChatGPT chat apps or websites. One of them is enough.

## How to install

1. Download `AIUsageMonitor-Setup-X.Y.Z.exe` from the Releases page.
2. Optional: check the file. In PowerShell, `Get-FileHash .\AIUsageMonitor-Setup-X.Y.Z.exe` must show the same SHA-256 as `SHA256SUMS.txt`.
3. Run it. The installer isn't code-signed yet, so Windows shows **"Windows protected your PC"** once: click **More info**, then **Run anyway**.
4. It installs to `%LOCALAPPDATA%\Programs\AIUsageMonitor` with Start menu and desktop shortcuts named **AI Usage Monitor (test)**. Tick **Start when I sign in** if you want it to start with Windows (you can change that later in the app's Settings).

To uninstall: Windows Settings > Apps > Installed apps > **AI Usage Monitor (test build)** > Uninstall. Your settings and history are kept unless you tick **Remove my data too**.

## How updates work

- Once a day the app asks GitHub for the number of the latest release in this repository. Nothing about you or your usage is sent. You can turn this off in **Settings > Updates**; the **Check for updates** button on the About page works either way.
- When a new version is out, a blue dot shows next to **About**. There is no popup.
- **Setup.exe installs:** **Download and install** downloads the new Setup.exe from this repository, checks it against `SHA256SUMS.txt`, closes the app for a few seconds while it installs, and opens it again. Your history and settings are kept. Nothing is installed without asking you.
- **All-users installs** (Program Files) can't update themselves. The app shows the download link to pass on to whoever installs software on that PC.

## Privacy

Everything stays on your PC. The app never asks for, reads or sends passwords, keys or tokens. Details: [PRIVACY.md](PRIVACY.md).

## Feedback

Bugs, ideas, or anything you don't like: **aiusagemonitor.feedback@gmail.com**. The app's About page has a **Send feedback by email** button that fills in the app and Windows versions.

---

Not affiliated with or endorsed by OpenAI, Anthropic or any other AI company. Product names belong to their owners.
