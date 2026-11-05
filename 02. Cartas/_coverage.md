# The letters of St Josemaría — what is here, and what is not

Audited 2026-08-22; **rewritten 2026-08-26**, when the folder went to one file per letter per
language and four letters arrived that the last audit said were not obtainable.

`build_register.py`'s register (`letters-register.json`, in the originals store since 2026-09-21 as `99. Tools/letters/register.json`) lists **36 numbered letters** (`04. Reference/letters-register.md`
has all 38, including the two the register omits). **Fourteen of the numbered letters are held in
full and three more as extracts**, and four more letters are held that are outside the numbered
series altogether.

---

## One file per letter per language

Alex's decision, 2026-08-26 (`open-questions.md` §4): *"we need to have just one copy of the
letters, with the commentary/footnotes."*

Letters 1–8 used to sit here twice in Spanish — the Rialp critical edition (`*.crit.es.md`) and the
official opusdei.org e-book (`*.es.md`) — sharing **447 anchors**, so `odsearch ref carta.19430531.39`
answered twice and `check_versions.py` reported it as its one real collision. The two were collated
point by point before anything was deleted (`99. Tools/letters/collate_official.py`, which reads
both from the EPUBs so the collation can be re-run after the second copy has gone):

> **447 anchors compared · 22 points differ at all · 4 are a real difference of reading.**

The other eighteen are the official e-book's typesetting: its footnote markers arrive glued to the
preceding word, its *ladillos* (the marginal headings) run into the text as ordinary paragraphs,
and it loses the space before an italic run. Its orthography is also the RAE's of 2010 —
`sólo`>`solo`, `ésta`>`esta`, 61 words — where the critical edition keeps St Josemaría's own
accentuation. **The critical text is what survives**, with its apparatus below it, and each file
quotes the official reading where the two differ.

### The four real variants, in full

| Letter | Point | Critical edition (the text held) | Official e-book |
|---|---|---|---|
| 6 | 18 | *Alguna vez ⟨—⟩ pensando en que…* — the word is **absent** | *Alguna vez **he** pensando en que…* |
| 6 | 75 | *con medios **ascéticos** y a través de formas apostólicas* | *con medios **acéticos*** — a misprint; the same e-book spells it *ascéticos* at n. 16 |
| 7 | 43 | *tanta sátira de ciertas manifestaciones **deteriores** de la caridad benéfica* | *manifestaciones **exteriores*** |
| 8 | 39 | *Este modo laical de servir a la Iglesia **vige** también en las labores…* | *…la Iglesia **rige** también…* |

Two of these are a difference of word (**7.43**, **8.39**) and are what a critical edition exists to
settle. One is plainly the e-book's misprint (**6.75**). One (**6.18**) is a word the critical
e-book does not print and the official one does; neither reading is comfortable Spanish and the
apparatus does not discuss it, so it is recorded and not decided.

### What the apparatus now is

Every critical-edition letter carries, **below its text and deliberately unanchored**:

- **the editor's study**, §§ 1–4 of the printed edition — *Contexto e historia*, *Fuentes y material
  previo*, *Cuestiones de crítica textual*, *Contenido* — with its own footnotes;
- **Notas del texto** (§ 6), the sources St Josemaría quotes, keyed to the `[n]` markers in the text;
- **the edition's marginal notes**, the modern references and the editor's glosses keyed to the
  paragraph (`1a`, `2b`) — volumes I and II only; volume III's e-book does not carry them;
- **the Aparato crítico** (§ 7), the variant readings of the manuscripts and printings.

Unanchored on purpose: an anchor would make Luis Cano's prose a citable unit of a document whose
`authority-type` is `founder`, and a search for what St Josemaría said would answer with what his
editor said about it. See `anchors.md` under the `carta` sigla.

Across the thirteen critical-edition letters: **354 blocks of the editor's study with its 76 notes,
901 *Notas del texto*, 813 marginal notes and 813 apparatus entries**. Nothing of those four
sections is left in the EPUBs. Two upstream misprints were repaired rather than carried, both in
letter 3 and both declared in its `repairs:` line — a note printed with its predecessor's number,
and a marker in the text printed as `[100]` where the sequence and the note's own content make it
121.

---

## Held — the numbered letters

| No. | Date | Incipit | Held as |
|---|---|---|---|
| 1 | 1930-03-24 | Singuli dies | `es` (crit) |
| 2 | 1931-03-24 | Videns eos | `es` (crit) |
| 3 | 1932-01-09 | Res omnes | `es` (crit) |
| 4 | 1933-07-16 | Vos autem | `es` (crit) + **`en`** |
| 5 | 1939-10-02 | Euntes ergo | `es` (crit) |
| 6 | 1940-03-11 | Sincerus est | `es` (crit) + **`en`** |
| 7 | 1942-10-24 | Quem per annos | `es` (crit) + **`en`** — new, see below |
| 8 | 1943-05-31 | Legitima hominum | `es` (crit) |
| 9 | 1944-02-14 | Opus nostrum | `es` (crit) |
| 10 | 1945-02-02 | Sacerdotes iam | `es` (crit) |
| 11 | 1945-05-06 | Divinus magister | `es` (crit) |
| 12 | 1946-04-30 | Numquam antehac | `es` (crit) |
| 14 | 1948-10-15 | Meum gaudium | `es` (crit) |
| 29 | 1959-01-09 | Dei amore | `es` + **`en`** (official e-book; no critical edition yet) |
| **28** | 1958-10-02 | Non ignoratis | **`es`, an extract** — 1,421 words, nn. 1–14 |
| **31** | 1961-01-25 | Gratias Deo | **`es`, an extract** — 1,188 words of a 73-page letter |
| **32** | 1962-05-25 | Ne proiicias | **`es`, an extract** — 3,417 words of a 90-page letter |

The three extracts came out of the opuslibros witness folder on 2026-08-26. They are the library's
only text of those three letters; each says in its own frontmatter that it is a 2011 transcription
from an unauthorised mirror, collated against nothing, and each carries `extract: true`. **Reading a
5% fragment as the letter is the obvious way to go wrong with this material** — that warning stands,
what has gone is the instruction never to cite it, which cannot stand when there is nothing else.

## Held — outside the numbered series

| Date | What it is | Anchor |
|---|---|---|
| 1958-05-23 | Letter to Francisco Franco on the *Principios Fundamentales*; published in *Razón Española* (2001) | `carta.19580523` |
| 1973-03-28 | The first *campanada*, nn. 1–20 | `carta.19730328.N` |
| 1973-06-17 | The second *campanada*, **nn. 36–39** — it continues the previous letter's numbering | `carta.19730617.N` |
| 1974-02-14 | The third *campanada*, nn. 1–29 | `carta.19740214.N` |

`carta-19730617.es.md` arrived wrapped in **21 numbered comments by an opuslibros contributor** —
polemic about the Work, with markers threaded through St Josemaría's sentences. They were stripped
(1,184 words of commentary; not one word of the letter was touched, verified by count) and the file
says so.

**The Burgos circular of 9-I-1939 was dropped, not promoted.** It is held already, and better: in
Alfredo Méndiz, "Tres cartas circulares del fundador del Opus Dei (Burgos, 1938-1939)", *Studia et
Documenta* 9 (2015), pp. 353-377 — `setd.9.2015.09`, an edition with apparatus and the AGP
shelfmarks. **71.5% of the transcription's 8-grams are in that article.** Cite Méndiz.

---

## The English of letter 7 — the correction this file owed

The 2026-08-22 audit recorded letter 7 as Spanish only, "no English obtainable". That was wrong.
`421024.DOC` has been in Alex's iCloud since at least 2003, under *Letter on the Work of St Raphael
Oct 1942*, and its Word properties name it outright: Subject "Letter 24-Oct-1942", Author **Brian
McCarthy**, Company **Lismulin Educational Foundation**, created 1998. Alex authorised its use on
2026-08-26 (tracker #76).

It is a **named translator's private typescript, not an official text** — opusdei.org has published
no English of this letter — and the file says so at the top and in `translation-status`. It marks
each point `#1`…`#70`, and the Spanish critical edition has exactly 70, so `carta.19421024.43`
resolves in both languages with no mapping. The original was **copied**, not moved: it is still in
iCloud, and a copy is in the store at
`01. Sources/San Josemaria/letters/_source/letter-07-quem-per-annos.en.doc` (sha256 verified equal).
`99. Tools/letters/extract_doc_en.py` converts it.

---

## Missing — nineteen numbered letters, and none of them is published

15 *Perfice gressus* · 16 *Bene nostis* · 17 *Via deflectit* · 18 *Hac nostra aetate* ·
19 *Hoc tempore* · 21 *Multa scripta* · 22 *Mirabilis omnino* · 23 *Vocationis vestrae* ·
24 *Sicut antea* · 25 *Divinus seminator* · 26 *Ad serviendum* · 27 *Multum usum* ·
30 *Dei voluntas* · 33 *Optime nostis* · 34 *In Opere Dei* · 35 *Veritatem facientes* ·
36 *Verba Domini* · 37 *Argentum electum* · 38 *Fortes in fide*

plus **13** *Ascendente eo* and **20** *In patientia*, which are absent from that `register.json`
altogether — not missing letters but gaps in its numbering, and both are in
`04. Reference/letters-register.md`.

The *Obras Completas* critical edition is being published volume by volume and has reached no. 14.
Until it goes further these letters exist here only as they are cited in other works.

## Where they were looked for

- **The three critical-edition EPUBs** — complete, text and apparatus alike.
- **The Biblioteca corpus.** `_markdown/SanJosemaria/0135 Cartas.md` indexes the letters with a page
  each — the *same fourteen*. It adds nothing, which is worth recording so the search is not
  repeated.
- **`cl docs/readings/St Josemaria Unpublished works/`** — nine titles, none of them a letter.
- **The opuslibros mirror** — eight pages, now dispersed: seven promoted (above), one dropped as a
  duplicate of `setd.9.2015.09`. `01. Sources/Opus Dei/_witnesses/opuslibros-2011/letters/` no
  longer exists.
- **Alex's iCloud** — which is where letter 7's English was, and where the next one may be.

## The tools

| | |
|---|---|
| `99. Tools/letters/extract_cartas.py` | the critical volumes: text and apparatus, one file per letter |
| `99. Tools/letters/apparatus.py` | §§ 1-4, 6 and 7 out of the three differently-built EPUBs |
| `99. Tools/letters/collate_official.py` | the collation against the official e-books; writes `collation.json` |
| `99. Tools/letters/extract_ebooks.py` | the official e-books — English 4, 6, 29 and Spanish 29 only |
| `99. Tools/letters/extract_doc_en.py` | the English of letter 7 from the 1998 typescript |
| `99. Tools/letters/promote_witnesses.py` | the opuslibros promotion, with the overlap measurements |
| `99. Tools/letters/register.json` (formerly `04. Reference/letters-register.json`) | the 36-letter register behind `04. Reference/letters-register.md`, whose themes that file now carries (#183) |
