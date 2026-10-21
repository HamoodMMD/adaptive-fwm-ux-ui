# Localization and international audiences

Interfaces used in a language other than English, in several countries, or by people from many places: translated text and its length, dates, times and time zones, numbers, currencies, plurals, names, addresses, phone numbers, units, sorting and choosing a language or region. Right-to-left direction and language switching are covered in `patterns/rtl-bilingual`; this module covers everything else.

**Load when:** the interface is in a language other than English, offers more than one language, serves more than one country or currency, has translation files, or shows dates, times, prices, names or addresses to an international audience.
**Skip when:** a single-language, single-country product with no plans to expand, and nobody asked.
**Pair with (when present):** `patterns/rtl-bilingual`, `patterns/forms`, `patterns/visual-scale`, `patterns/tables`, `profiles/booking-reservation`.

## Objectives

Each person reads the interface in their language without truncated or overlapping text, and sees dates, times, numbers, prices, names and addresses the way they write them. Nothing depends on English word order or Western name and address formats. People choose their language and region and keep that choice.

## Priority principles

1. **Layouts make room for any language.** Short English labels can double or triple in length in translation.
2. **Never guess a reader's language from their location.** Use their stated preference and the browser's language, and let them change it.
3. **Format with the locale, not by hand.** Dates, numbers, currencies, plurals and lists follow the user's locale through the platform's formatting tools.
4. **Do not assume Western formats** for names, addresses, phone numbers or calendars.
5. **Never write or fix translations you cannot verify.** Report untranslated or wrong text; translation is recommend-only work.

## Checks

### Text length and layout
- Buttons, tabs, labels, table headers, badges and navigation grow with their text. Fixed widths, single-line truncation of labels, and text fitted tightly into images or shapes are findings.
- Short strings expand most: under 10 English characters can become two to three times longer in European languages.
- Long compound words (German, Finnish, Dutch) can break narrow layouts; they need room or hyphenation in the right language.
- Chinese, Japanese and Korean text may be shorter in characters but wider per character; Thai, Arabic and Devanagari need more line height.
- Abbreviations made to fit English space are avoided; other languages may not abbreviate.
- The first screen still shows the key message and action in the longest supported language.

### Strings built correctly
- Sentences are not assembled from fragments ("You have " + n + " new " + item): word order differs between languages.
- Plurals use the locale's plural rules; languages have up to six forms (zero, one, two, few, many, other), so "item(s)" and adding "s" are findings.
- Text in images, icons that are letters, and screenshots in the wrong language are reported as untranslated.
- Untranslated strings, mixed languages on one screen, and English-only error messages and emails are findings.

### Dates and times
- Dates follow the locale's format. Where readers from several countries see the same page, the month is written as a word or the format is shown, because 03/04 means March or April depending on the reader.
- Times show the time zone whenever people in different zones see them (bookings, events, deadlines, logs), using city names to help people find their zone.
- Times meant as local wall-clock times (opening hours, a birthday, a hotel check-in) are not shifted by the viewer's zone; times on a shared timeline (a webinar start, a log entry) are shown in the viewer's zone with the zone named.
- The first day of the week, 12 or 24 hour clock and calendar system follow the locale where the product supports them.

### Numbers, money and units
- Decimal and thousands separators follow the locale (26,254.39 in English is 26.254,39 in German).
- Prices show the currency clearly where several currencies are possible, with the symbol or code placed as the locale expects.
- Units match the region (metric or imperial, Celsius or Fahrenheit, paper sizes) or are shown in both where the audience is mixed.
- Number inputs accept the locale's decimal separator.

### Names, addresses and phone numbers
- A single "full name" field is preferred; where names are split, labels avoid "first" and "last" and family name is not required.
- Name fields accept long names, any script, single letters, spaces, hyphens and apostrophes, and do not change case.
- Address fields suit the countries served: postcode and state are not forced where they do not exist, and the country is chosen first when it changes the format (`patterns/forms`).
- Phone fields accept international numbers with a country code and common punctuation.

### Choosing language and region
- The product starts from the user's saved choice, then the browser's language, then a sensible default. Location by IP is not used to choose the language, only perhaps to suggest a region.
- Links to the other languages are on every page, each written in its own language (`patterns/rtl-bilingual`).
- Language and region (for currency, shipping, formats) are separate choices where they differ, for example English in the UAE.
- The choice is remembered.

### Sorting and search
- Lists sort in the locale's alphabetical order, not by raw character codes.
- Search tolerates accents and the locale's variants where the product supports it.

## Anti-patterns

- A redirect to a country site by IP with no way back.
- "1 file(s) deleted".
- Buttons cut off in German or French.
- 04/05/2027 shown to a mixed US and European audience.
- A booking time with no time zone.
- "First name" and "Last name" both required.
- A required "State" field for a country without states.
- Prices with a bare "$" on a site serving several dollar currencies.

## Exceptions and context

- **Single-country products** need only that locale's formats; they still accept names and addresses of people from elsewhere where that is likely.
- **Global business software** often shows ISO dates (2027-05-04) on purpose for clarity; that is acceptable when consistent.
- **Legal and financial documents** may require a fixed language or format; the interface says so.

## Implementation cautions

- Safe UI work: letting containers grow with text, removing fixed widths, adding a time-zone label already known to the product, showing the currency code, relabeling name fields, removing a required flag from a field that does not apply.
- Functional work, recommend only: adding a language or region, changing locale detection, plural and formatting logic, time-zone handling, translation files and keys, address formats per country.
- Never machine-translate into the product, and never edit translations you cannot verify.

## Sources

- [W3C-38] Text length grows in translation; shorter strings grow most; flexible layouts; line height for some scripts
- [W3C-39] Personal names around the world: single field, no first/last labels, permissive validation
- [W3C-40] Date formats: avoid ambiguity, month names or ISO dates, page language context
- [W3C-41] Choosing language: do not guess from IP, links on every page, remember the choice
- [W3C-42] Time and time zones: show the zone, city names, wall-clock versus timeline times
- [UNI-01] Plural categories by language
- [MDN-06] Locale-aware formatting of dates, numbers, plurals, lists and sorting
