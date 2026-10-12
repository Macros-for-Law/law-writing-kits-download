# Law Writing Kits: SJTEIL Kit + Legal Kit (v7)

Two add-ins for **Microsoft Word on a Mac** that add three ribbon tabs:

| Tab | For |
|---|---|
| **SJTEIL Write** | Drafting your Note: template styles, body word counts, hidden scaffolding, citation and style checks, live *supra* / *infra* cross-references, short cites, Source Tracker sync |
| **SJTEIL Edit** | Tech-editing an assignment: tracked fixes with TLR / Bluebook rule comments, scan-and-fix tools, Perma.cc links, anonymized copies, the LAE report |
| **Legal Writing** | Memos and briefs: assignment settings, legal styles, outlines, PBTS / CRAC frames, Check Memo, Bluebook or Washington citation style, Table of Authorities |

Press **F10** in Word for the Tool Library: every tool, its shortcut, and exactly what it does. Hovering over a button shows the same description.

## Install

No account or sign-in is needed to download.

1. **Download** `Law-Writing-Kits-v7.zip` from the [latest release](https://github.com/Macros-for-Law/law-writing-kits-download/releases/latest) (Assets) and double-click it to unzip. You get a **Law Writing Kits** folder.
2. If you have never opened Word on this Mac, open it once. Then **quit Word**.
3. In the folder, **double-click `Install.command`**. A Terminal window opens; answer its question (if any) and press Return at the end.
   - If macOS says it can't verify `Install.command` (the kit isn't from the App Store): click **Done**, open **System Settings › Privacy & Security**, scroll to **Security**, click **Open Anyway** next to "Install.command", then **Open**, and enter your Mac password if asked. (macOS 14 or earlier: right-click `Install.command` › Open › Open.)
   - If macOS asks whether Terminal may access data from other apps, click **Allow**: the installer copies the add-ins into Word's own folder.
   - A way that always works: open Terminal, type `bash ` (with a space), drag `Install.command` into the window, and press Return.
4. **Open Word** and click **Enable Macros** if asked. The three tabs appear.

Optional: Word › Settings › View › Ribbon › *Show group titles*, and System Settings › Keyboard › *Use F1, F2, etc. keys as standard function keys* (otherwise hold **fn** with the F-key shortcuts).

**Read Me First.txt** in the folder covers first steps, Find Rule, Source Tracker sync, Perma.cc links, Anonymize Copy, privacy, and troubleshooting (also attached to each release as Read-Me-First.txt).

### Requirements
- A Mac with Word for Microsoft 365, or Office 2019 or later. Windows is not supported.
- Sync Tracker, Add Source, Add Perma Link, and Anonymize Copy also use Apple's free Command Line Tools (the installer checks; to add them, run `xcode-select --install` in Terminal).
- Add Perma Link needs your own Perma.cc account. Find Rule opens your own Bluebook (22d) and TLR Manual PDFs; the kits contain no text from either book.

### Update or uninstall
- **Update:** download the new release, quit Word, and run its `Install.command` the same way. It replaces the add-ins and tools and asks before replacing your Note template (your copy is backed up).
- **Uninstall:** quit Word and run `Uninstall.command` the same way. It asks before removing the Note template, the Source Tracker backups, or a saved Perma.cc key. Your documents are never touched.

### Privacy
Everything runs on your Mac. The one exception is Add Perma Link / Perma Setup, which send the URL being archived and your Perma.cc API key to api.perma.cc. The key is stored only in your Mac's Keychain.

## Report a bug or suggest a feature
You need a free GitHub account to post. Open the **[Issues](https://github.com/Macros-for-Law/law-writing-kits-download/issues)** tab › **New issue** › *Bug report* or *Feature request*. Please don't paste confidential draft text, client facts, or text copied from the Bluebook, TLR Manual, or course materials; rule numbers are enough.

To see where a suggestion stands, check its label (**planned**, **considering**, **not planned**, **shipped**) and the pinned [Roadmap](https://github.com/Macros-for-Law/law-writing-kits-download/issues/1) issue.

## Shortcuts (⌃ is Control, not ⌘)
- F2 Paste Plain · F3 Join Lines · F4 Body Text · F5/F6 Italicize/Unitalicize Case · F7 Id. · F8 Count Selection ·
  F9 Show/Hide Scaffolding · F10 Tool Library · F11 Track Changes · F12 Tech-Edit Mode
- ⌃⌥ + Q D W E L G K A (Standardize), B Count Body Words, C Check Cites, S Check Style, R Add Rule, F Add Flag,
  U Insert Supra, O Insert Short Cite, H Add Perma Link, I [sic], N/M en/em dash, P Post Footnote Notes, X Run All Scans,
  ↑/↓ Move Section
- Legal: ⌃⌥⇧ + 1–4 headings, B block quote, N case name, G signal, I Id., O Insert Short Cite, 7 §, P ¶, T mark authority,
  W word count, M Check Memo, C Check Cites, S Check Style. Word built-ins: ⌘⌥1–3 headings, ⌘⌥O Outline view (drag headings), ⌘⌥⇧V plain paste.
- F2, F3, F8, F9, F10 and Standardize are bound by both kits with identical behavior.
- On a Mac with the Claude for Word add-in, ⌃⌥C is also its shortcut; Word asks which to run. Use the Check Cites button.
