# Privacy policy - AI Usage Monitor

Last updated: October 14, 2026 (version 0.9.12)

AI Usage Monitor is a small Windows app that shows your Claude Code and Codex usage limits. This page says what it does with your data. Short version: everything stays on your PC.

## What stays on your PC

- Your settings, your usage history and the app's logs are kept in `%LOCALAPPDATA%` on your PC. They are never uploaded anywhere.
- The usage numbers come from Claude Code and Codex on your PC: the app asks those tools for them. Claude Code and Codex contact Anthropic and OpenAI the way they normally do; the app itself does not.
- Daily goal and session alerts are worked out on your PC. A Windows notification is shown by Windows on your PC; nothing about it is sent anywhere.
- **Export / Print** (History) makes a PDF report or CSV file on your PC, in the folder you choose, or sends the report to the printer you pick. The app uploads nothing. If you save into a folder that OneDrive (or another cloud service) syncs, that service uploads the file like any other file there; the app tells you when the folder is a OneDrive folder. The PDF holds no user name, computer name, folder path, account or e-mail.

## Passwords, keys and tokens

The app never asks for, reads, stores or sends passwords, API keys or sign-in tokens. Each tool uses its own sign-in. When a sign-in has expired, the app's **Sign in** button opens that tool's own login window.

## The one network call

The app makes one network call: once a day it asks GitHub for the latest version number. It requests this repository's latest release from `api.github.com`:

`GET https://api.github.com/repos/rick-ronen/ai-usage-monitor-releases/releases/latest`

- The request sends no personal data and no usage data. It carries only the app's name and version (`User-Agent: AIUsageMonitor/X.Y.Z`), no account, no cookies.
- GitHub sees your IP address, like it does for any website you visit. GitHub's own privacy statement covers that.
- You can turn the daily check off in **Settings > Updates**. The **Check for updates** button on the About page then still works, but only when you click it.

If you click **Download and install**, the app downloads the new installer and its checksum file from this repository's releases on GitHub. Nothing is downloaded or installed without your click.

## What the app does not do

- No tracking, no analytics, no ads, no crash reports sent anywhere.
- No account with us, and no server of our own.

## Questions

Email **aiusagemonitor.feedback@gmail.com**.

---

Not affiliated with or endorsed by OpenAI, Anthropic or any other AI company. Product names belong to their owners.
