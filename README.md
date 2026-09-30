# Tapless dictionaries

Word lists for [Tapless](https://github.com/Pixxel123/tapless.koplugin), the
swipe keyboard plugin for KOReader. The plugin's dictionary manager reads
`catalog.json` from this repository's GitHub Pages site and downloads the
packages from its releases.

## Version 2.0.0

Eleven languages: Czech, Danish, Dutch, English, French, German, Italian,
Polish, Portuguese (Brazil), Spanish and Turkish. Each package keeps the
words and frequencies of the 1.0.0 package (from
[wordfreq](https://github.com/rspeer/wordfreq)), and adds:

- **Capitals**, from the word counts of the
  [Leipzig Corpora Collection](https://wortschatz.uni-leipzig.de): a word
  written capitalized at least 95% of the time is stored that way, so
  German nouns, names, days and "I" are typed with their capital, while
  words like "march" are not.
- **Missing words**, from the same counts, up to 150,000 words, ranked
  below the words the list already had.
- **Less junk**: words that neither [Wiktionary](https://www.wiktionary.org)
  (through [kaikki.org](https://kaikki.org)) nor the corpora know are left
  out, such as laughter, words typed without their accents and web debris.

Measured on words of [Tatoeba](https://tatoeba.org) sentences, swiped
cleanly, against 1.0.0 (words fixed / broken): Danish +73/−0, Turkish
+52/−1, German +23/−4, Dutch +13/−1, Spanish +10/−0, Italian +7/−0,
Portuguese +6/−1, French +5/−0, English +4/−0, Polish +4/−0, and Czech +9/−17
(13 of them one name).

The packages are built by `tools/build_dictionary.py` in the plugin's
repository, from sources `tools/fetch_dictionary_sources.py` downloads.

## Licences

Each package holds its own `ATTRIBUTION.txt` and licence files.

- wordfreq data: see `LICENSE-wordfreq.txt` and `DATA-LICENSE.txt` in each
  package.
- Leipzig Corpora Collection word counts: CC BY 4.0.
- English word pairs: counted from Tatoeba sentences, CC BY 2.0 FR.
- Wiktionary is only used to decide which words to leave out; no
  Wiktionary text is included.
