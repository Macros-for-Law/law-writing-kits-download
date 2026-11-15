# Law Writing Kits: SJTEIL Kit + Legal Kit (v8.7)
Two add-ins for **Microsoft Word on a Mac or a Windows PC** (Windows is in beta) that add three ribbon tabs:

| Tab | For |
|---|---|
| **SJTEIL Write** | Drafting your Note: template styles, body word counts, hidden scaffolding, citation and style checks, live *supra* / *infra* cross-references, short cites, Source Tracker sync |
| **SJTEIL Edit** | Tech-editing an assignment: tracked fixes with TLR / Bluebook rule comments, scan-and-fix tools, Perma.cc links, anonymized copies, the LAE report |
| **Legal Writing** | Memos and briefs: assignment settings, legal styles, outlines, PBTS / CRAC frames, Check Memo, Bluebook or Washington citation style, Washington appellate and trial briefs (record cites, word-count certificate, Table of Authorities) |

Both kits also have **Verify Cites** and **Pull Source**: free online checks of every citation (cases, statutes, regulations, court rules, executive orders, bills, reports, dockets, articles, books, Restatements, web links) that send only the citation's parts, never your text.

Press **F10** in Word for the Tool Library: every tool, its shortcut, and exactly what it does. Hovering over a button shows the same description. **Help › Kit Settings** sets each kit's defaults (your journal, style manual, check output letters, shared documents, Perma folders).

Working in a shared Teams or OneDrive document? Add **P** to a check's letters: its tracked fixes and comments go into a private local copy, and the shared document is not touched.

**Which computer?** [Mac](#install-on-a-mac) · [Windows (beta)](#install-on-windows-beta)

## Install on a Mac

**Fastest:** quit Word, open Terminal, paste this line, and press Return (it downloads the latest version and runs the installer; no security prompts):
```
cd /tmp && curl -fsSLo lwk.zip https://github.com/Macros-for-Law/law-writing-kits-download/releases/latest/download/Law-Writing-Kits.zip && rm -rf "Law Writing Kits" && unzip -q lwk.zip && bash "Law Writing Kits/Install.command"
```

Or by hand:

1. **Download** [`Law-Writing-Kits.zip`](https://github.com/Macros-for-Law/law-writing-kits-download/releases/latest/download/Law-Writing-Kits.zip) from the [latest release](https://github.com/Macros-for-Law/law-writing-kits-download/releases/latest) (Assets) and double-click it to unzip. You get a **Law Writing Kits** folder.
2. If you have never opened Word on this Mac, open it once. Then **quit Word**.
3. In the folder, **double-click `Install.command`**. A Terminal window opens; answer its question (if any) and press Return at the end.
   - If macOS says it can't verify `Install.command` (the kit isn't from the App Store): click **Done**, open **System Settings › Privacy & Security**, scroll to **Security**, click **Open Anyway** next to "Install.command", then **Open**, and enter your Mac password if asked. (macOS 14 or earlier: right-click `Install.command` › Open › Open.)
   - If macOS asks whether Terminal may access data from other apps, click **Allow**: the installer copies the add-ins into Word's own folder.
   - A way that always works: open Terminal, type `bash ` (with a space), drag `Install.command` into the window, and press Return.
4. **Open Word** and click **Enable Macros** if asked. The three tabs appear.

Optional: Word › Settings › View › Ribbon › *Show group titles*, and System Settings › Keyboard › *Use F1, F2, etc. keys as standard function keys* (otherwise hold **fn** with the F-key shortcuts).

**Read Me First.txt** in the folder covers first steps, Verify Cites and Research Accounts, Find Rule, Source Tracker sync, Perma.cc links, Washington briefs, Anonymize Copy, privacy, and troubleshooting (also attached to each release as Read-Me-First.txt).

### Requirements (Mac)
- A Mac with Word for Microsoft 365, or Office 2019 or later.
- Sync Tracker, Add Source, Add Perma Link, Verify Cites, Pull Source, Build Cite Table, and Anonymize Copy also use Apple's free Command Line Tools (the installer checks; to add them, run `xcode-select --install` in Terminal).
- Add Perma Link needs your own Perma.cc account; Verify Cites needs a free CourtListener account to check cases (other keys are optional). Find Rule opens your own PDFs: use your own copy of the Bluebook (22d), the TLR Manual (15th), and the Washington OAH Style Manual. The kits contain no text from them and link to no copies. The Washington style sheet is a public court rule: [GR 14 Appendix 1](https://www.courts.wa.gov/court_rules/pdf/GR/GA_GR_14_Appendix.pdf).

### Update or uninstall (Mac)
- **Update:** download the new release, quit Word, and run its `Install.command` the same way. It replaces the add-ins and tools and asks before replacing your Note template (your copy is backed up).
- **Uninstall:** quit Word and run `Uninstall.command` the same way. It asks before removing the Note template, the Source Tracker backups, or a saved Perma.cc or research key. Your documents are never touched.

## Install on Windows (beta)

Beta: tested on one Windows 11 laptop with 64-bit Word. The release notes list what has not been tested on Windows yet.

1. **Download** [`Law-Writing-Kits-Windows.zip`](https://github.com/Macros-for-Law/law-writing-kits-download/releases/latest/download/Law-Writing-Kits-Windows.zip) from the [latest release](https://github.com/Macros-for-Law/law-writing-kits-download/releases/latest).
2. If you have never opened Word on this PC, open it once. Then **close every Word window**.
3. Right-click the zip and choose **Extract All**. Open the extracted **Law Writing Kits** folder. (Install does not work from inside the zip.)
4. **Double-click `Install`** (its type is "Windows Batch File"). A black window opens; answer its question (if any) and press Enter at the end.
   - Windows asks before running a downloaded file. If you see **"Open File - Security Warning"**, click **Run**. If you see **"Windows protected your PC"** instead, click **More info**, then **Run anyway**.
   - Install only copies files into your own user folders. It asks for no administrator password and changes no Windows or Word setting.
5. **Open Word** and click **Enable Content** if a yellow bar asks. The three tabs appear.

Laptops: if F2-F12 change the brightness or volume, hold **Fn** with them, or turn on Fn Lock (often Fn+Esc).

**Read Me First.txt** in the folder is the Windows version of the guide (also attached to each release as Read-Me-First-Windows.txt).

### Requirements (Windows)
- A Windows 10 or 11 PC with desktop Word (Microsoft 365, or Office 2019 or later). Word in a browser cannot run the kits.
- Nothing else to install: the zip carries its own private copy of Python (python.org's embeddable package) for Sync Tracker, Add Source, Add Perma Link, Verify Cites, Pull Source, Build Cite Table, Find Rule page jumps, and Anonymize Copy.
- School accounts: if Word is signed in with a school email, the school's IT settings decide whether macros run. The kits were tested with one school account and worked. If the tabs don't appear, see Troubleshooting in Read Me First.

### Update or uninstall (Windows)
- **Update:** download the new zip, close Word, extract it, and run its Install. The add-ins you had are kept as "(previous version)" copies in the kit's backups folder.
- **Uninstall:** close Word and double-click `Uninstall` in the extracted folder. It asks before removing the Note template, your backups, saved keys, or your Kit Settings. Your documents are never touched.

### Shortcuts on Windows
The table below applies with **Ctrl+Alt** for ⌃⌥ and **Shift** for ⇧. Two keys differ so Word keeps its own: **Add Flag** is Ctrl+Alt+Shift+F (Ctrl+Alt+F stays Insert Footnote) and **Make Em Dash** is Ctrl+Alt+Hyphen (Ctrl+Alt+M stays New Comment).

### Privacy
Everything runs on your own computer except tools you start that go online:
- **Add Perma Link / Perma Setup** send the URL being archived and your Perma.cc API key to api.perma.cc.
- **Verify Cites / Check Connections** send only each citation's own parts (a case's volume, reporter, and page; a code section; an article title; a URL), never your text, to free public services: CourtListener, GovInfo, eCFR, the Federal Register, the Washington Legislature and courts.wa.gov, Cornell LII, Congress.gov, Regulations.gov, Open States, OpenAlex, Crossref, Open Library, the Internet Archive, and the cited site. Results are cached on your Mac for 30 days.
- **Preemption Check** (SJTEIL Kit) sends only the search terms you type to api.openalex.org, after you confirm, and opens Google Scholar and SSRN searches with those terms in your browser.
- **Pull Source** and **Find Rule** open a page in your browser.

Keys are stored only in your Mac's Keychain (on Windows, in Windows Credential Manager). Check Cites' reporter rules are generated from Free Law Project's [reporters-db](https://github.com/freelawproject/reporters-db) (BSD 2-Clause).

## Report a bug or suggest a feature
Open the **[Issues](https://github.com/Macros-for-Law/law-writing-kits-download/issues)** tab › **New issue** › *Bug report* or *Feature request*. Please don't paste confidential draft text, client facts, or text copied from the Bluebook, TLR Manual, or course materials; rule numbers are enough.

To see where a suggestion stands, check its label (**planned**, **considering**, **not planned**, **shipped**) and the pinned [Roadmap](https://github.com/Macros-for-Law/law-writing-kits-download/issues/1) issue.

## Shortcuts (⌃ is Control, not ⌘)
- F2 Paste Plain · F3 Join Lines · F4 Body Text · F5/F6 Italicize/Unitalicize Case · F7 Id. ·
  F9 Show/Hide Scaffolding · F10 Tool Library · F11 Track Changes · F12 Tech-Edit Mode
- ⌃⌥ + Q D W E L G K A (Standardize), B Count Body Words, C Check Cites, S Check Style, R Add Rule, F Add Flag,
  U Insert Supra, O Insert Short Cite, H Add Perma Link, I [sic], N/M en/em dash, P Post Footnote Notes, X Run All Scans,
  ↑/↓ Move Section
- Legal: ⌃⌥⇧ + 1–4 headings, B block quote, N case name, G signal, I Id., O Insert Short Cite, 7 §, P ¶, T mark authority,
  W word count, M Check Memo, C Check Cites, S Check Style. Word built-ins: ⌘⌥1–3 headings, ⌘⌥O Outline view (drag headings), ⌘⌥⇧V plain paste.
- F2, F3, F9, F10 and Standardize are bound by both kits with identical behavior.
- On a Mac with the Claude for Word add-in, ⌃⌥C is also its shortcut; Word asks which to run. Use the Check Cites button.
