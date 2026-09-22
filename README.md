# Bimo data

The data files bundled in [Bimo](https://apps.apple.com) (笔墨), an iPad
app for learning Chinese characters, published here because the
licenses of their sources require modified versions to be available to
anyone under the same terms. The app's own code, memory tips, word
hints, component stories and audio are not part of this repository.

| File | What it is | Made from | License |
|---|---|---|---|
| `strokes.json` | Stroke outlines and stroke medians for every character in the deck | [hanzi-writer-data](https://github.com/chanind/hanzi-writer-data), which repackages [Make Me a Hanzi](https://github.com/skishore/makemeahanzi)'s graphics, drawn from Arphic Technology's PL KaitiM GB and PL UKai fonts | [Arphic Public License](licenses/ARPHICPL.txt) |
| `chardetails.json` | Each character's structure (components and their roles), radical, and origin note | Make Me a Hanzi's `dictionary.txt` (itself built on Unihan and CJKlib); radicals replaced with Unihan's kRSUnicode | [GNU Lesser General Public License v3](licenses/LGPL-3.0.txt) (with the [GPL v3](licenses/GPL-3.0.txt) it refers to); Unihan data under the Unicode License |
| `vocab.json` | The HSK 3.0 word list, levels 1 to 6, with pinyin and definitions | [complete-hsk-vocabulary](https://github.com/drkameleon/complete-hsk-vocabulary) (word list, MIT) and its CC-CEDICT definitions | [MIT](licenses/MIT-complete-hsk-vocabulary.txt) for the list; [CC BY-SA 4.0](licenses/CC-BY-SA-4.0.txt) for the definitions |
| `sentences.json` | Example sentences with English translations, up to two per word | [Tatoeba](https://tatoeba.org), sentence numbers and contributors in each entry | [CC BY 2.0 FR](https://creativecommons.org/licenses/by/2.0/fr/); a few entries without a contributor were written for Bimo and are CC BY-SA 4.0 |

## Changes made to the sources

Stated here because the Arphic license, CC BY-SA and the LGPL ask for it.

- **strokes.json** (Arphic): one file for the whole deck instead of one per
  character; each entry keeps the stroke outlines as SVG path strings and
  the stroke medians as point lists exactly as the source has them, in
  its 1024-unit box; characters outside the deck are omitted. No glyph
  was redrawn or simplified.
- **chardetails.json** (LGPL): the radical field is taken from Unihan
  rather than Make Me a Hanzi's; component roles (meaning, sound) and
  the origin notes were corrected and rewritten where scholarship
  disagrees with the source (for example 租 as a phono-semantic compound
  of 禾 and 且); entries are limited to the deck's characters and their
  components.
- **vocab.json** (MIT and CC BY-SA): definitions shortened and reworded
  for learners, a handful of readings corrected (胖 pàng, 挑 tiāo and
  others), words ordered within each level by frequency.
- **sentences.json** (CC BY): converted to simplified characters with
  OpenCC; sentences chosen for cloze safety and screened for tone.

These changes were made between June and September 2026 by the author
of Bimo. The files are regenerated from their sources by scripts in the
app's repository; this copy is updated whenever the app's bundled data
changes.

## Using these files

You may copy, modify and redistribute each file under its license above.
The Arphic license requires `licenses/ARPHICPL.txt` to accompany any copy
of `strokes.json` unaltered. CC BY-SA requires attribution and the same
license on adaptations of the definitions. CC BY requires naming the
Tatoeba contributors, which each sentence entry carries as `by` (the
sentence) and `enBy` (the translation).
