# Changelog

## v8 (October 2026): online research checks and Washington briefs

### New
- **Verify Cites** (both kits; ⌃⌥V on SJTEIL Edit, ⌃⌥⇧V on Legal Writing): checks every citation in your saved draft
  against free public sources and sends only each citation's own parts, never your text. Cases (CourtListener),
  federal statutes, regulations, and the Federal Register (GovInfo, eCFR; a dated C.F.R. or U.S.C. cite is checked
  against that year's edition), executive orders, Washington RCW / WAC and court rules, federal court rules (Cornell
  LII), bills, committee and CRS reports, agency dockets (Congress.gov, Regulations.gov, Open States), articles and
  books (OpenAlex, Crossref, Open Library), Restatements (series and subject), web links (with Internet Archive
  copies of dead links), and your own short forms, *Id.*, supra, and infra. Choose what to check and what to produce:
  **T** tracked fixes (only one-answer fixes: a reporter spelling, a Federal Register date, an executive order's first
  page), **C** `[Cite Verify]` comments, **R** a report. Westlaw / Lexis numbers and other states' statutes are listed
  as not checkable. Results are cached on your Mac for 30 days.
- **Pull Source** (⌃⌥J / ⌃⌥⇧J): opens the free copy of the citation at the cursor (CourtListener, GovInfo, eCFR,
  Congress.gov, court rules, the state's code site, or the web page).
- **Research Accounts** menu: set up free keys (CourtListener for cases; optional api.data.gov, OpenAlex, Open States),
  stored only in your Keychain. **Check Connections** tests every service and lists what it covers and its limits.
- **Build Cite Table** (SJTEIL Edit › Footnotes): one row per citation in your assigned footnotes, with type, pincite,
  Perma link, and Verify Cites status, ready to paste into Excel.
- **Check Cites** adds reporter-abbreviation fixes (from Free Law Project's reporters-db), signal commas, and a
  pincite-before-first-page check, each with a tracked fix or comment as you choose (T / C / R).
- **Washington briefs** (Legal Writing): Court of Appeals and trial-court motion brief outlines, **Check Record Cites**
  (CP / RP form, ranges, uncited facts), **Certify Word Count** (RAP 18.17), **Mark Authority** and **Insert Table of
  Authorities** with brief headings, and brief checks in Check Memo (format, word limit, sections).
- **Anonymize Copy** also highlights personal data (email addresses, phone numbers, IP addresses, SSN-shaped numbers).

### Changed
- Checks and scans skip text inside web addresses (a Perma ID's hyphen is not a range).
- Every check that can change your draft asks once what to produce (T / C / R) and remembers your answer per tool.

### Privacy
- Verify Cites, Check Connections, Pull Source, and Find Rule's Washington rules are the kits' new network uses; see the
  Read Me's Privacy section for the exact services. Nothing goes out unless you run one of them.

## v7 (October 12, 2026): first release on GitHub

### New
- **Hover text = Tool Library.** Every button's tooltip is its full description (what it changes, whether it is tracked,
  and the rule); menus list their items. F10 shows the same text, plus extra notes in small grey type.
- **Insert Short Cite** (both kits; ⌃⌥O on SJTEIL Write, ⌃⌥⇧O on Legal Writing): type a party name and it writes the
  short form with your pin cite, offers *Id.* when the previous cite is the same case, and warns when the case has no
  full citation yet or the full cite is more than five footnotes back (Bluebook R. 4.1, R. 10.9).
- **Clear Formatting** (SJTEIL Write › Draft): strips pasted fonts, sizes, colors, highlighting, and underlining but
  keeps your paragraph style, italics, bold, small caps, and footnote marks.
- **Legal Writing**
  - **Assignment Settings:** page or word limit, spacing, Bluebook or Washington citation style, required sections,
    and your From line, saved in the document.
  - **Check Memo** (⌃⌥⇧M): length against your limit, missing or out-of-order sections, leftover prompts, and
    structure slips (a rule with no citation, a case description with no pincite or no reasoning, a case group that
    opens with a case name, an argument with no mini-conclusion, opinion words, quotation-heavy paragraphs). Report only,
    with optional `[Memo Check]` comments.
  - **Analysis group:** Insert Case Group, Insert Argument (analogize, distinguish, or integrated), issue statements
    (Under–Does–When or Whether–When), brief answers, and Color-Code Formula.
  - **New outlines:** Full Memo, E-Memo, Client Advice Letter, and Email to Supervising Attorney.
  - **Washington style:** Check Cites adds Washington citation checks, and Find Rule has Washington topics that open
    your own copy of the style manual.
- **Perma.cc folder picker** opens your folders one level at a time (type part of a name, U to go up, N for a new
  subfolder after a confirmation).

### Changed
- **Condense Paste is now Join Lines** (F3, both kits). It replaces only line breaks, so italics in the joined text stay.
- Legal Writing's old Clear Formatting is now **Reset to Normal**.

### Fixed
- Remove Scaffolding, Remove Prompts, and the placeholder counts now find scaffolding while it is hidden.
- Anonymize Copy retries its save once when Word's file permission arrives a moment late.
- The installer instructions cover macOS 15 and later (Open Anyway in Privacy & Security).

### Known issues
- If another add-in uses ⌃⌥C (for example Claude for Word), Word asks which one to run; click Check Cites on the
  ribbon instead.
- The kits are unsigned, so Word may ask you to Enable Macros each time it starts.
