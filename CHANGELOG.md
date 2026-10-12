# Changelog

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
