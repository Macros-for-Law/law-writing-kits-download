# Changelog

## v8.7 (November 2026): Windows beta, two Washington citation styles, fewer repeated comments, faster Check Cites

### Windows (beta)
- **The kits now run in Word for Windows** (Microsoft 365, or Office 2019 or later; Windows 10 or 11). Download
  `Law-Writing-Kits-Windows.zip`, extract it, close Word, and double-click **Install**. It copies files into your own
  user folders only: no administrator password, and no Windows or Word setting changes. **Uninstall** removes them and
  asks before removing your template, backups, saved keys, and Kit Settings.
- The zip carries its own private copy of Python for Sync Tracker, Verify Cites, Add Perma Link, Find Rule page jumps,
  and Anonymize Copy. Keys are kept in Windows Credential Manager.
- Shortcuts are the Mac ones with **Ctrl+Alt** for Control+Option. Two differ so Word keeps its own: Add Flag is
  Ctrl+Alt+Shift+F and Make Em Dash is Ctrl+Alt+Hyphen.
- **Why beta:** tested on one laptop (Windows 11, 64-bit Word, a school account): build, compile, every regression case,
  the installer and uninstaller, and Find Rule. See the release notes for what has not been tested on Windows yet.
- Find Rule on Windows reads the page count of any PDF (a scanned Bluebook and a compressed style sheet read as 0
  pages before), so it can warn about a different edition.

### Two Washington citation styles (Legal Kit)

- **Washington: Exceptions to Bluebook** is a new citation style (Assignment Settings > 4, and Kit Settings for the default).
  It follows GR 14 Appendix 1, the Reporter of Decisions style sheet: a Wn.2d, Wn.3d, or Wn. App. cite stands alone (no
  parallel P.3d cite is asked for), Wash. is the first series, a Washington case cited only to P.2d / P.3d is a check item
  (exc. 9), a year after a current RCW section is a check item (exc. 13), and comments cite the sheet's exception numbers.
  Check Style adds one note per document for % and one for numbers in text (exc. 4, 5).
- **Washington Style Manual** is the new name of the old "Washington Style Sheet" style, which follows the OAH Style
  Manual's citation guide (Wn.2d with the parallel P.3d; pincite after the Washington page). Its checks are unchanged,
  and documents already set to it keep it; comments now say WA Style Manual. Both Washington styles know Wn.3d.
- **Washington brief outlines** set Exceptions to Bluebook when the document has no citation style (was the manual style).
- **Find Rule** has 12 topics for the sheet and keeps the manual's topics; a document set to one Washington style lists
  that style's topics. The sheet (3 pages) and the manual (28 pages) are separate PDFs, each remembered on its own.
- Fixture WX Cite Test; word_regress cases "cites WX" and "style WX" (29 cases).

### Fewer comments, same information (both kits)
- **One comment for a repeated typeface finding** (Check Cites): Id., supra, or a signal that is not italic 10 or more times
  (or Id. never italic or underlined anywhere, 3 or more times) gets one comment at the first place, with the count. T
  still fixes every place, and the report lists each one, marked [report only].
- **Passive voice** (Check Style): a comment only where a paragraph has two or more possible passives (one comment names
  them). A single passive is listed in the report, with the count and the rate per 1,000 words.
- **Sentence length** (Check Style): a comment at 50 words or more; sentences of 41-49 words are listed in the report only.
- **The test's own words** (Check Style): a style word is skipped when the same two-word phrase appears inside quotation
  marks elsewhere in the document ("actually used").
- **Legal Kit:** the "who will read this?" Washington note is no longer a finding; the report's Citation style line says it.
- **SJTEIL Kit:** one comment per name and footnote for "footnote N does not mention Name"; 10 or more hyphen page ranges
  become one report line that points to Scan Ranges; a section number that continues a list of sections is not a range.
- The report's FINDINGS line now ends with "Report only: N" when some findings have no comment.

### New checks
- **Quotation marks that do not pair up**, and **a run-in quotation of 50 or more words** (BB R. 5.1(a); TLR 7.06), in
  Check Cites, both kits. Comments only. A quotation that runs over several paragraphs is fine.
- **A semicolon or colon inside a closing quotation mark** (TLR 1.08): T moves it outside as a tracked change.
- **Legal Kit, Check Style:** a court called they / their; ", however," or ", therefore," between two full sentences.
- **Both kits, Check Style:** an abbreviation used before the parenthetical that defines it (TLR 1.05(b)).
- **Legal Kit, Check Memo:** optional page-format lines (Assignment Settings 9) and the Brief Answer's opening word
  (Assignment Settings 10), both off by default; "outcome but no reasoning" accepts more ways of giving the reasoning.
- **SJTEIL Kit: Insert Sub Edit Memo** (SJTEIL Edit > Report): a Sub Edit Memo outline in a new document.

### Fixed and faster
- A closing quotation mark followed by a case name with no reporter cite, and a Washington cite with a no-break space, no
  longer raise an error inside Check Cites (the match was skipped and the report carried an error note).
- Check Cites and Check Style skip the search for any plain pattern that is nowhere in the text, and footnote numbers are
  looked up from a list built once per run.
- The helper script refuses arguments that hold anything but letters, digits, spaces, and hyphens.
- Removed three unused procedures.

## v8.6 (October 2026): Page Fit, case names, quotation and footnote-mark checks, safer Check Cites

### Removed (both kits)
- **Count Selection (F8)** is gone from both ribbons and the shortcut is unbound. Word's status bar shows the selected
  words; Count Words (Legal) still reports the selection, and Count Body Words (SJTEIL) is unchanged.

### New (Legal Kit)
- **Check Page Fit** (Count & Check): pages against the limit, the lines and words past it, where each Heading 1-2 section
  starts and how long it runs, and the three longest paragraphs. Read-only; it never touches margins, fonts, or spacing.
- **Italicize All Cases** (Format): every Name v. Name, and later one-word mentions of a case, after a confirm that gives the
  counts. A short name two cases share, and titles like Judge Ortega, are skipped.
- **Index Case Names** (Cite): hidden Table of Authorities marks (Cases) on each mention, then a Table of Cases at the cursor.

### New (Check Cites)
- **Quotation without a source** (both kits): a quotation of 8 or more words with no footnote after it (SJTEIL) or no citation
  or footnote (Legal) is a check item. A quotation inside a parenthetical is skipped. Block quotations are not checked.
- **Footnote mark placement** (SJTEIL Kit): a footnote number before a comma, period, semicolon, or closing quotation mark, or
  two numbers in a row, is a check item (a dash is the exception). Neither rule names a rule number.
  On the nine unedited journal articles (1,434 footnote numbers): 10 quotation items and 31 mark items.

### New (Check Cites, both kits): one run, shorter comments, CourtListener
- **One run, no hidden findings.** Findings are collected first and written at the end, so a tracked fix never hides a later
  check on the same citation. A warning appears when tracked deletions are still pending (Word keeps deleted text visible to a
  macro).
- **Comments say what to fix:** the faulty part is shaded, and the comment reads title, the citation as written, the fix, then
  the rule and where to read it. The R. 1.2 summary now lists every signal.
- **V (new output letter): CourtListener check.** Looks up each full case citation and compares court, year, and name; a
  wrong year is a tracked fix. Only the volume, reporter, and first page are sent, and only when you choose V and have set up
  your own CourtListener token (Research Accounts).

### New (SJTEIL Kit)
- **Check Note lists each [VERIFY]** with its page or footnote and the words around it (the first 15).

### Fixed
- **A run-time error no longer loses a whole Check Cites or Check Style run.** Each rule that fails is skipped and named in
  the report; an error anywhere else keeps the findings so far, puts Track Changes, screen updating, and the status bar back,
  and says what stopped. Before, such an error left Track Changes on.
- **Check Cites: a citation with no second party** (Smith v. 123 F.3d 45) raised error 5 in the missing-volume check.
- **Check Record Cites / brief checks (Legal Kit): three Mid$ errors** when a paragraph starts with ER, RCW, RAP, CR, or GR
  and a number, or when a page range runs to the start of the text.
- **Check Memo's page count** could read a page short (the page-count statistic lags the layout in current Word): the page the
  last character sits on is now the floor, so a 2-page memo no longer passes a 1-page limit. Check Page Fit uses the same count.
- Verify Cites says when it stopped at 300 distinct cases; the pending-deletions count reads each revision once.
- `shared/lint_vba.py` now flags an And / Or whose right side slices with a subtracted index (VBA runs both sides).

## v8.5 (October 2026): law-review footnotes, memo misses, and two tech-edit fixes

### Fixed (SJTEIL Kit)
- **Scan Numbers no longer edits a supra's footnote number.** In "supra note 2" made with Insert Supra, the 2 is a
  live cross-reference; the scan used to offer to spell it out (supra note two), breaking the link. Every scan now
  skips text inside a field, and the footnote log no longer shows field code next to an edit.
- **Serial Commas works.** The scan never found a series in Word. It now asks at a clear list missing its serial
  comma: three or more short items (price fixing, division of markets, group boycotts and tying) or one-word items
  (large, unregulated and unprotected). On nine journal articles it asked about 2 times per article. A three-item list
  with longer items is not caught.

### New (SJTEIL Kit): Check Cites for law-review footnotes
- **Periodical names in small caps.** A journal name between its volume and first page (41 Harbor L. Rev. 1101) that is
  not in small caps draws a finding; T applies Small Caps as a tracked formatting change (names typed in capitals are
  only flagged). A roman article title right before it is a check item.
- **More italics:** lowercase id. (see id.), See, e.g., and In re / Ex parte case names in a full footnote citation
  (a check item, like the v. names).
- **supra and hereinafter:** supra 4 and supra n. 4 become supra note 4 (tracked); supra note N that points to this
  footnote or a later one, or to a footnote that does not mention the name, is a check item (Insert Supra keeps the
  number current); supra for a case is a check item; (hereinafter X) becomes [hereinafter X] and a roman hereinafter
  is italicized (both tracked).
- **Id. after a string citation:** a footnote that starts with Id. right after a footnote with more than one authority
  is a check item.
- **En dash ranges in article pages** (315-22) are now read; Pub. L. numbers still keep their hyphens.
- **Footnote periods:** a nonbreaking space after the final period no longer draws a false finding, and a period
  typed inside a closing parenthesis ((2d Cir. 2024.), (2d ed.)) no longer counts as the footnote's period.

### New (both kits): law-review footnotes
- **Perma.cc per URL:** each URL needs its own bracketed Perma.cc link, not one per footnote.
- **v. followed by a nonbreaking space** gets every v.-based check (date, pincite, citation shape, typeface).
- **(accessed** becomes **(last visited**, and **Fed. R. Evid. Rule 901** becomes **Fed. R. Evid. 901** (tracked);
  two authors joined by and before an italic title is a check item (use &).

### New (both kits): Check Cites catches the errors it missed most in memos
- **No period before a citation:** a closing quotation mark right before a citation (T puts the period inside the
  quotation marks), a capital Id. right after a lowercase word (T adds the period), and a check item when a full
  citation follows a lowercase word that does not lead into a case name.
- **See Id.:** Id. after a signal or citing / quoting is lowercase (T fixes it).
- **citing / quoting outside a parenthetical:** after a pincite, a closing parenthesis, or Id., it goes in its own
  parenthetical.
- **Case-name abbreviations (T6):** words such as Department, Office, Attorney, Corporation in a full citation's case
  name; in a sentence that names the case, only Corporation, Company, Association, Brothers, Incorporated, Limited,
  Number, and. T fixes a name with one such word.
- **Short form with a date** now draws a finding in Bluebook mode too (it did only in Washington mode); T deletes the
  parenthetical. **at before a full citation's pincite** (575, at 583): T deletes at.
- **In re / Ex parte** cites get the date, pincite, and citation-shape checks, and their short forms are checked.
- **Government parties:** when the first party is an office, district, county, or attorney, the short name is the
  other party (Check Cites and Insert Short Cite).

### Fixed (both kits)
- **Short forms on the line after a full citation** are checked now: the short-form check no longer reads back into
  the previous paragraph's full citation (or ahead into the next paragraph's case name) and skips the short form.
- **Short form with a date** no longer fires on a full citation to a numbered title (Annual Report 1990-1995, at 12
  (1996)); a full case citation with at before its pincite (999 F. Supp. 938, at 940) gets the at finding instead.

### New (Legal Kit): two Check Memo checks
- **Check Memo: missing roadmap** (Legal Kit, memos). When the general rules (the Legal Standard section, or the
  opening of the Discussion) never say which elements are undisputed and which the memo analyzes, Check Memo adds one
  comment on the heading where the roadmap belongs. A short one-part Discussion with no sub-headings is not checked,
  and neither are briefs (their Summary of Argument does that job).
- **Check Memo: more first-person forms.** "We can rely", "we could rely", "we would rely", "we should rely", "we rely
  on", "we can point to", and "we could point to" are flagged like "we can argue". "We can show" is left alone, since
  a client letter uses it for the firm.

## v8.4 (October 2026): comments a first-year can act on

### Changed
- **Check Cites: Washington Reports with the parallel P.3d** (Bluebook mode). The comment now asks who will read the
  document: Washington courts and classes that teach the Washington Style Sheet keep both reporters (and the comment says
  where to switch: Assignment Settings > Citation style); strict Bluebook cites the P.3d only. It rebuilds your own
  citation (State v. Smith, 405 P.3d 997, [P.3d page] (Wash. 2017)) and warns that a Wn.2d pincite is not a P.3d page.
- **Comments that may be fine as written** now start "Possible issue:" instead of "check:", and the Check Cites report
  says what that means.
- **Legal Kit: no TLR Manual references.** Check Style labels read Verbosity, Legalese, Qualifier, Informal, Passive
  voice, Style tip; the doubled-period comment is labeled Punctuation; "Read:" no longer points to TLR pages.
- **Legal Kit: memo wording** in the Kit summaries for signals (R. 1.2), Id. (R. 4.1), numbers (R. 6.2), and websites
  (R. 18.2), which were written for law-review footnotes and SJTEIL; six more (R. 3.2, 3.3, 5.3, 8, 16.6, 18.3) drop
  their TLR or SJTEIL sentence.
- **Check Cites report** (Legal Kit, Bluebook mode) names the citation style and where to change it.
- Clearer wording: supra (no comma between supra and note), (citation modified), a repeated full citation with one
  party, and the missing-date example for P.2d / P.3d cases ((Wash. 2019), (Wash. Ct. App. 2019)).

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
