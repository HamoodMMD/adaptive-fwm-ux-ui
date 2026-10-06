# Informational content

Sites and sections whose job is to let people find, read and move through information: knowledge bases, documentation, guides, institutional and public-sector sites, editorial and reference content.

**Load when:** reading and finding are the main tasks and there is little or no transaction.
**Skip when:** the content exists mainly to sell (use `sales-lead-generation` or `b2b-marketing`), or the surface is an application.
**Journey:** arrive (often deep, from search) → confirm this is the right page → scan → read → go to related information.
**Pair with (when present):** `patterns/navigation`, `patterns/search-filter-sort`, `patterns/tables`, `patterns/responsive-mobile`.

## Objectives

A reader can tell at once whether a page answers their question, find the part they need without reading everything, trust where the information came from and how current it is, and reach related material without going back to the start.

## Priority principles

1. **Most visitors arrive mid-site and scan.** Every page must orient a reader who has seen nothing else.
2. **Structure is the interface.** Headings, summaries, lists and links do the work that controls do in an application.
3. **Organize by what users look for,** not by the organization's departments.
4. **Reading comfort is functional.** Measure, size, spacing and contrast decide whether long content gets read.
5. **Keep it a content site.** Do not import application patterns that the task does not need.

## Checks

### Information architecture and findability
- Sections and labels reflect users' topics and vocabulary. A newcomer can predict what is under each heading.
- Categories are distinct; a page has one obvious home even if it is linked from several places.
- Hierarchy is as shallow as the volume allows; deep content is reachable by more than one route: navigation, search, and an index, sitemap or hub pages.
- Hub and landing pages summarize what is in a section and route onward; they are not empty link lists.
- Breadcrumbs appear on sites with three or more levels.
- Navigation shows where the current page sits.

### Page orientation
- The title says what the page is about in the reader's terms and matches the link that led there.
- A short summary or opening paragraph states what the page covers and who it is for.
- Publication date, last-updated date and author or owning body are shown where currency or authority matters.
- The page's place in a series or section is visible, with previous and next where order matters.

### Content hierarchy and scanning
- The most important information comes first; background and detail follow.
- Headings are frequent, descriptive and hierarchical, so the outline alone tells the story.
- Paragraphs are short and carry one idea. Sets are lists; sequences are numbered; comparisons are tables.
- Key terms may be emphasized sparingly; emphasis is not used for whole paragraphs.
- Long pages (several screens with four or more sections) have a table of contents or in-page navigation; short pages do not need one.
- Callouts for warnings, notes and prerequisites are visually distinct and used consistently.

### Reading typography
- Body text is large enough to read comfortably on each device and uses the brand's text face at a legible weight.
- Line length is moderate. About 70 to 80 characters per line is a common upper bound, and 80 is the limit in WCAG's enhanced (AAA) guidance. Very long lines and very short ones both make reading harder.
- Line height is generous for body text; paragraphs are clearly separated.
- Text is aligned to the reading start edge, not fully justified.
- Contrast meets the requirements for body text; links are distinguishable by more than color.
- Text can be zoomed to 200% and reflows without horizontal scrolling.

### Links and related content
- Link text describes the destination; it makes sense read out of context.
- Related pages are offered where they help: inline where relevant and at the end, chosen for the reader's likely next question.
- External links are identifiable; links to files state the type and size.
- No dead ends: every page offers an onward route.

### Search
- Search is easy to find on content-heavy sites and covers what users expect it to cover; if it is limited to a section, that is stated.
- Results show title, a relevant snippet and the section or type; the query stays visible and editable.
- No-results pages suggest alternatives. Detail: `patterns/search-filter-sort`.

### Credibility of information
- Sources are cited or linked for facts and figures; data has a date.
- Authorship or institutional ownership is clear, with a route to contact or correct.
- Outdated content is marked as such, archived or removed, not left to look current.
- Opinion, sponsored material and advertising are distinguishable from reference content.

### Documents, media and tables
- Information is published as web pages in preference to PDFs; documents that must be files are accessible and described.
- Images that carry information have text alternatives; decorative ones do not distract.
- Data tables have headers and captions and remain usable on small screens. Detail: `patterns/tables`.
- Code samples, where present, are in real text with a copy action.
- Video and audio have captions or transcripts and never autoplay with sound.

### Documentation specifics (where applicable)
- Version or product selector is visible and its current value clear.
- A persistent sidebar shows structure; the current page is marked; long sidebars are collapsible by section.
- Steps are numbered, one action per step, with the expected result stated.
- Prerequisites come before the steps.

## Anti-patterns

- Navigation that mirrors the org chart.
- Pages that open with a hero image and marketing copy before the answer.
- Walls of text with no headings.
- Headings chosen for font size; skipped levels.
- "Click here", "this link", bare URLs.
- Essential information locked in PDFs.
- Undated content on topics that change.
- Infinite scroll on reference content, hiding the footer and losing the reader's place.
- Interstitials, newsletter pop-ups and sticky promotions over the text.
- Onboarding tours, dashboards, gamification or account walls on a site whose users only came to read.
- Full-width text lines on large monitors.
- Carousels for important content.

## Exceptions and context

- **Editorial and long-read features** may use immersive layouts and larger imagery; reading comfort and orientation still apply.
- **Legal and regulatory texts** must keep their wording and structure; add summaries, anchors and navigation around them.
- **Reference tables and data portals** are closer to `dashboard-analytics` and `patterns/tables` than to prose rules.
- **News and feeds** can suit continuous loading for browsing, with a load-more control to keep the footer reachable.
- **Small sites** (a handful of pages) do not need search, breadcrumbs or a table of contents.
- **Specialist audiences** need precise terms; plain structure still helps them.

## Implementation cautions

- Typography, spacing, measure, heading levels, link text, landmark structure and table markup are UI-safe.
- Changing URLs, section structure or navigation taxonomy affects bookmarks, inbound links and search visibility: recommend with a redirect plan.
- Content usually lives in a CMS or Markdown source. Fix templates; list content-level issues (missing dates, unclear titles, long paragraphs) for the content owners instead of rewriting articles wholesale.
- Do not alter facts, figures, citations or dates. Do not add authorship or update dates that the source does not record.
- Search behavior, indexing and ranking are functional. Presentation of results is UI.

## Sources

- [NNG-24] How users read on the web — scanning, concise structure
- [GOV-06] GOV.UK writing guidelines — user needs, front-loading, plain language
- [NNG-15] Breadcrumbs
- [NNG-30] Infinite scrolling — unsuitable for goal-directed finding
- [NNG-18] No-results pages
- [W3C-01] WCAG 2.2 — 2.4.5 Multiple Ways, 2.4.6 Headings and Labels, 2.4.4 Link Purpose, 1.4.8 Visual Presentation (AAA, line length)
- [WEB-08] Responsive basics — readable line length
- [STAN-01] Web credibility — verifiability, currency
- [NNG-11] Comprehensive, correct and current content
- [W3C-18] Accessible tables
- [W3C-19] Text alternatives for complex images
