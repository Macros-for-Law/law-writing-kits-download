# Changelog

## v8.3 (October 2026): every part of a citation

### New
- **Check Cites: citation structure** (both kits). Each case citation is checked for all its parts. A full citation
  missing its volume, reporter, first page, or the comma before the volume says which part is missing; one that starts
  with no case name, or repeats a case without its second party, gets a check. A short form of a case cited in full
  earlier (Byrne, 328 F.3d at 382) that is missing its volume, reporter, "at", pincite, or the comma after the name, or
  that keeps the first page (328 F.3d 379, at 382), is flagged, and with T the fix is a tracked change, since the full
  citation gives the right volume and reporter. *Id.* with no "at" (Id. 382) gets a tracked "at"; "Id. at" with no page
  is flagged.

### Fixed
- **Check Cites**: a full citation missing its reporter (328 379, 382) or first page (328 F.3d, 382) said "no pincite";
  it now says which part is missing.

## v8.2.1 (October 2026): missing pincites and a date-check fix

### New
- **Check Cites: missing pincite** (both kits). A full case citation with its date parenthetical but no pincite gets a
  check item (BB R. 3.2(a); Bluepages B10.1.2). Not flagged: a case named in your own sentence ("In Smith v. Jones, ...,
  the court"), See generally, short forms, Westlaw / Lexis numbers, and Table of Authorities lines.

### Fixed
- **Check Cites**: a citation whose pincite and date were deleted ("328 F.3d 379,." once Word closes up the space) is
  flagged for its missing date again; it was skipped as not a citation.
- **Check Cites**: Table of Authorities lines typed by hand (dot leaders or a tab before the page numbers) are skipped
  by the date and pincite checks.
- **Verify Cites**: with a stray comma left before the period, a missing date is a comment, not a tracked insertion.

## v8.2 (October 2026): citation dates and case names in italics

### New
- **Check Cites: date parentheticals** (both kits). A full case citation with no court-and-year parenthetical is flagged
  (BB R. 10.4, 10.5), and an F.3d / F.4th or F. Supp. citation whose parenthetical has no circuit or district gets a check.
- **Verify Cites: dates** (both kits). A verified case whose date parenthetical is missing, or gives a different year than
  CourtListener's, is a check item; with T, a missing one is added after the pincite as a tracked change (the court comes
  from one CourtListener search, made only for those citations).
- **Check Cites: case names in italics** (Legal Kit). The full name is checked from the party before v. to the party after
  it (an italic v. no longer passes a roman name), and a case cited in full keeps its name italic in short forms (a finding)
  and in later mentions (a check, since a party or witness can share the name).

### Changed
- **Check Cites: section in citations** (both kits). "section" or "Sec." right after U.S.C. or C.F.R. is flagged in the
  body, not just footnotes, with a regular or non-breaking space ("Under section 2615, ..." in a sentence is left alone).
  In Washington style "U.S.C. section" is a check, since the Style Sheet allows the word in text for U.S.C. sections.
- **Washington-style memos** get the page-span, "at" before §, §§, and et seq. checks too: the Washington Style Sheet makes
  no exception to those Bluebook rules.

### Fixed
- **Check Cites**: underlined case names (allowed in Bluebook-style memos) are no longer flagged as not italic. In
  Washington style, where the Style Sheet wants italics, they still are.

## v8.1 (October 2026): Kit Settings, private copies, and fewer false positives

### New
- **Kit Settings** (Help, both kits): defaults for every document on your Mac. SJTEIL Kit: your journal (SJTEIL, Law
  Review, SJSJ, AILJ, other), style manual (TLR Manual + Bluebook, or Bluebook only), Note length, the mode a new Note
  opens in, check output letters, shared documents, and Perma folders. Legal Kit: output letters, shared documents, and
  the citation style and From line for new documents. Asked once, the first time you use a kit tool.
- **P = private local copy** in the output question of Check Cites, Check Style, Verify Cites, Check Record Cites, and
  Check Memo: tracked fixes and comments go into a dated copy in Documents › Law Writing Kits › Local Copies, so a shared
  Teams or OneDrive document isn't touched. Bring work back by copying the fixes you keep, or Review › Compare › Combine.
- **Preemption Check** (SJTEIL Write › Count & Check › More Checks): searches OpenAlex for articles that may overlap your
  topic (only your search terms are sent, after you confirm), opens Google Scholar and SSRN searches, and logs the date
  and terms in your draft; Check Note shows the last check.
- **Check Cites** (Bluebook 22d): page spans keep only the last two digits (tracked fix), no "at" before § (tracked fix),
  §§ for several sections and no et seq., an explanatory parenthetical after See also, Cf., But cf., Compare, Contrast,
  and See generally, Inc. after Co. or Corp., the regional reporter only for Washington cases in law reviews and
  Bluebook memos, aff'd / rev'd / cert. denied (tracked fix), U. for Univ. in journal titles, and 24-hour timestamps.
- **Find Rule**: 23 more topics (citation sentences, business firm designations, parallel and public-domain citations,
  briefs and court filings, ordinances, bills, agency adjudications, state administrative materials, manuscripts,
  working papers, web timestamps, treaties, U.N. documents, tribal nations, tables T2-T4, T8, T9) and updated summaries.

### Changed
- **Add Perma Link** asks which Perma.cc folder each link goes in (Return = the last one; pick another; a new subfolder,
  created only when you OK the archive). Kit Settings can turn the question off.
- **Build Cite Table** lists the footnotes that cite books first, so you can request them early.
- **Brief outlines** (Legal Writing): each argument point gets separate prompts (topic sentence, rule, case groups with
  a PBTS, argument with record cites, mini-conclusion) and the Argument starts with a roadmap; CREAC prompts match.
- **Pull Source** opens Washington bills (bill summary) and U.N. documents (by symbol).
- **Check Style** (both kits) skips citation sentences (Id., Smith v. Jones, 1 F.3d 2 ...) and doesn't count quoted
  words or a citation inside a sentence toward sentence length; the report shows how many citation sentences it skipped,
  so the readability numbers measure your own prose.

### Fixed
- **Check Cites**: "spell out Section at the start of a sentence" no longer fires on 29 U.S.C. §, C.F.R. §, Id. §, or
  Wash. Prac. §; "v., not vs." no longer fires outside case names (federal vs. state).
- **Check Style**: "rather than" is no longer flagged as a hedge; aff'd and rev'd are not contractions; you / your are
  not flagged in letters and emails (Dear ...); stative wording (was entitled, is based) is not flagged as passive voice;
  "is required to" gets one comment, not two.
- **Sentence reading** (Check Style, Check Memo, Check Record Cites): Id. followed by a new sentence ends its own
  citation sentence, and abbreviations in citations (U.S.C., C.F.R., Jud., Cnty., Att'y ...) no longer split one.
  Check Record Cites counts an Id. citation as the record cite for the facts before it; Check Memo reads "Similarly,
  just as in [case], ..." as an analogy, not another case description.
- **Verify Cites**: a real case that CourtListener has by name but without its reporter citation is a check item
  ("confirm the volume and page"), not "Not found".

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
