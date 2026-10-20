# Privacy policy - AI Usage Monitor

Last updated: October 15, 2026 (version 0.9.16)

AI Usage Monitor is a small Windows app that shows your Claude Code and Codex usage limits. This page says what it does with your data. Short version: everything stays on your PC.

## What stays on your PC

- Your settings, your usage history and the app's logs are kept in `%LOCALAPPDATA%` on your PC. They are never uploaded anywhere.
- The usage numbers come from Claude Code and Codex on your PC: the app asks those tools for them. Claude Code and Codex contact Anthropic and OpenAI the way they normally do; the app itself does not.
- Daily goal and session alerts are worked out on your PC. A Windows notification is shown by Windows on your PC; nothing about it is sent anywhere.
- **Runs** (History > Runs) are read from the session files Claude Code and Codex keep on your PC (`%USERPROFILE%\.claude\projects` and `%USERPROFILE%\.codex\sessions`). The app reads only numbers and names: the times, the model, token counts (input, output, cache write, cache read, reasoning), how many tool calls there were (counted, never read), whether a subagent ran, the effort level, and the **last folder name** of the folder a run worked in (for example `my-project`, never the full path or your user name). It never reads, keeps, shows, logs or exports your prompts, the replies, tool input or output, or file contents. It never changes those files. What it keeps is a small summary of numbers per run (`runs.json`), so runs stay in History after Claude Code deletes its old files. Reading runs makes no network call.
- **API value** is an estimate: what a run would cost at the public pay-as-you-go API prices of the date shown (from Anthropic's and OpenAI's pricing pages). It is not your bill and not what your plan costs.
- **Project names** show in the app by default; exports and PDFs say "Project 1, 2, 3" unless you turn names on (Settings > Runs). You can rename or hide a project.
- **More accurate runs (optional):** if you add the app's small status line script to Claude Code yourself (Settings > Runs > Copy setup), Claude Code passes it its own cost estimate, run time, effort level and folder name after each reply; the script saves only those numbers and the folder name in the app's data folder. The app never edits Claude Code's settings.
- **Export / Print** (History) makes a PDF report or CSV file on your PC, in the folder you choose, or sends the report to the printer you pick. The app uploads nothing. If you save into a folder that OneDrive (or another cloud service) syncs, that service uploads the file like any other file there; the app tells you when the folder is a OneDrive folder. The PDF holds no user name, computer name, folder path, account or e-mail.

## How long your history is kept, and how to delete it

- By default, usage readings and runs are kept until you delete them. In **Settings > Storage** you can keep only the last months or years (old data is deleted in whole months, at the first start of each month; a backup CSV is saved first), set a size limit (warn, or delete the oldest month), save all data as a backup ZIP, and **Clear history** for days, months, years or a range of dates (today can't be cleared). Missed checks are kept for 90 days (you can clear them, or single entries, in **History > Missed checks**); logs up to 5 MB each.
- Uninstalling with **Remove my data too** deletes the whole data folder.

## Passwords, keys and tokens

The app never asks for, reads, stores or sends passwords, API keys or sign-in tokens. Each tool uses its own sign-in. When a sign-in has expired, the app's **Sign in** button opens that tool's own login window.

## The one network call

The app makes one network call: at every start and once a day (at the time you choose) it asks GitHub for the latest version number. It requests this repository's latest release from `api.github.com`:

`GET https://api.github.com/repos/rick-ronen/ai-usage-monitor-releases/releases/latest`

- The request sends no personal data and no usage data. It carries only the app's name and version (`User-Agent: AIUsageMonitor/X.Y.Z`), no account, no cookies.
- GitHub sees your IP address, like it does for any website you visit. GitHub's own privacy statement covers that.
- You can turn the daily check off in **Settings > Updates** (then the app checks only when it starts). The **Check for updates** button on the About page always works.

If you click **Download and install**, the app downloads the new installer and its checksum file from this repository's releases on GitHub. Nothing is downloaded or installed without your click.

## Crash reports

If the app closes unexpectedly, it writes what happened to `crash.log` in its data folder on your PC. At the next start it offers a short report (you can turn this off in **Settings > General**; **About > Send a problem report** shows the same report at any time).

- **What is in it:** the app version, how it was installed, the Windows version, language and region, the time of the crash (UTC), the error type, code and message, the error's location in the app's code (file name and line), the last 20 screens or controls you used (names only, like "History > Runs"), and the last 30 lines of the app's log.
- **What is removed before you see it:** file and folder paths, your Windows user, computer and domain names, email addresses, web addresses (except this repository), project names and labels, long IDs, and every number that could be usage, tokens, dollars or times (they show as `<number>`).
- **Nothing is sent by the app.** You see the whole report first. **Send by email** only opens a draft in your own email program, addressed to the feedback address; it is sent only if you press Send there. A long report is saved as a text file for you to attach. **Copy**, **Save as file** and **Don't send** are always there.

## What the app does not do

- No tracking, no analytics, no ads. No crash report is sent anywhere unless you send it yourself by email.
- No account with us, and no server of our own.

## Questions

Email **aiusagemonitor.feedback@gmail.com**.

---

Not affiliated with or endorsed by OpenAI, Anthropic or any other AI company. Product names belong to their owners.
