# The *Diccionario*'s citations of St Josemaría — what does not resolve, and why

Written 2026-09-01 (od-e7). This is the register tracker **#102** points at. It replaces the row's pointer to `_unresolved.tsv`, which never held these: that file is the citation-graph sidecar written by `99. Tools/links/citation_links.py`, 1,208 rows of `src_anchor · decode_target_work · label · reason` recording decode wikilinks that could not be resolved to an anchor. Different question, different columns, added by a later commit. **Nothing anywhere recorded the 163.**

Machine-readable form beside this file: `_miscitations.tsv`.

## The headline

**The row's number does not reproduce, and its own three worked examples are all false alarms.**

| | |
|---|---|
| quotation-carrying citations of `C S F ECP AD CONV` found | **2,519** (2,495 direct, 24 behind `cfr.`) |
| tested (direct, quotation ≥ 3 tokens, cited anchor exists) | **2,450** |
| resolve at the anchor cited | **2,423 — 98.9 %** |
| do not | **27** |
| cite an anchor that does not exist (`ECP 213`, `ECP 283`; ECP has 187 points) | 2 |
| quotation too short to test (< 3 tokens) | 43 |
| **confirmed mis-citations, each with the true anchor named** | **26** |
| quotation not located anywhere in the six works | 1 |

The row said "1,069 of 1,232 match (87 %), 163 do not". On roughly twice the sample the figure is **98.9 %, and 26 real errors**.

## The row's own three examples

All three were checked by hand first, before any count was believed.

**`(S, 983)`.** The row says the *Diccionario* quotes *«Un día sin mortificación es un día perdido»* while `surco.983` reads *«Sin mortificación no hay felicidad en la tierra»*, and calls them "different points". They are — but the *Diccionario* cites **both**, in one parenthesis, after **two** quotations:

> …san Josemaría llegue a afirmar con palabras netas: "Sin mortificación, no hay felicidad en la tierra", y "Un día sin mortificación es un día perdido" **(S, 983, 988)**.

`surco.983` is the first quotation, word for word. `surco.988` is the second: *"Un día sin mortificación es un día perdido, porque no nos hemos negado, no hemos vivido el holocausto."* **The *Diccionario* is right and the check paired the last quotation with the first number.**

**`(AD, 35)`.** Four citations in the *Diccionario*. All four quote `ad.35` verbatim — different fragments of one long point that runs from *"Esclavitud por esclavitud…"* to *"…no somos hijos de la esclava, sino de la libre"*. All correct.

**`(ECP, 17)`.** Three of the four are correct: `ecp.17` runs `17a`–`17h`, and it contains *"hemos de estimar especialmente la obediencia"* (17a), *"Soy muy amigo de la libertad…"* (17b), *"Siempre intentamos ser reyes, aunque sea del reino de nuestra miseria"* (17d) and *"Miremos de nuevo el ejemplo de Cristo. Jesús obedece…"* (17h). The fourth, in `filiacion-divina.es.md`, is a real error — the text is `ecp.65`.

## The three explanations the row said were never tested

### (a) The *Diccionario* cites an edition whose point numbering differs — **REFUTED**

This was the expensive possibility, and it is dead. Three independent reasons:

1. **8 of the 26 errors have the right number and the wrong work.** `(F, 420)` is `surco.420`; `(C, 737)` is `surco.737`; `(AD, 145)` is `ecp.145`; `(CONV, 24)` and `(CONV, 26)` are `ecp.24` and `ecp.26`; `(ECP, 93)` and `(ECP, 94)` are `conversaciones.93` and `conversaciones.94`; `(ECP, 283)` is `camino.283`. A difference of numbering between editions cannot produce a citation whose number is right in a *different* book.
2. **The 15 same-work errors have no offset.** They scatter: −90, −20, −2, −1, −1, −1, +1, +1, +1, +9, +37, +48, +50, +100, +581. A re-numbered edition gives a systematic drift, not this.
3. **2,423 of 2,450 land exactly on the number cited.** Two different numbering spaces do not agree 98.9 % of the time.

**The *Diccionario*'s numbering and this library's `camino` / `surco` / `forja` / `ecp` / `ad` / `conversaciones` spaces are the same space.** That is the finding the row wanted, and it is the reassuring one.

### (b) The quotation spans a chunk boundary and the match failed mechanically — **CONFIRMED, and it is most of the 163**

Five specific ways the original check could fail on a correct citation, each found here:

- **A multi-number citation was scored against the first number only.** `(S, 983, 988)`, `(AD, 5, 19)`, `(CONV, 113-115)` — the honest target is the concatenation of every point cited.
- **`cfr.` citations were treated as quotations.** *"apostolado de la doctrina" (cfr. S, 172)* is the *Diccionario*'s own phrase in scare quotes; `surco.172` is about temptation and was never claimed to say it.
- **Footnote markers.** The anchored text carries them as bare digits — *"erat subditus illis 65, obedecía"* — where the *Diccionario* prints the reference — *"erat subditus illis (Lc 2, 51), obedecía"*. Any literal or k-gram match dies on that.
- **One substituted word erases a short quotation.** `(C, 463)` quotes *«Más que en «dar», a caridad está en «comprender»»*; `camino.463` reads *"Más que en "dar", la caridad está en "comprender"."* One dropped `l`, and every 5-gram of a 9-word quotation fails. The citation is perfect.
- **The text under test was replaced the next day.** The row is dated 27 August. On 28 August `88966e501` replaced the whole corpus in place — *"Monte Carmelo epub text replaces the decode in place, on the same anchors"* — **294 files, 9,093 insertions, 6,532 deletions**. The decode's `examen-de-conciencia.es.md` read *"cuando se ama de veras, siempre se encuentran…"*; the epub restores the ellipsis the decode had dropped, *"de veras..., siempre"*. Whatever the 163 measured, it measured a text that is no longer here.

### (c) The *Diccionario* mis-cites — **CONFIRMED**, and it is the residue

26 cases, each verified by finding where the quotation actually is. Three were opened line by line against both texts before any of this was written down:

- `(ECP, 94)` in `matrimonio.es.md` — *"Bendigo a los padres que, recibiendo con alegría la misión que Dios les encomienda, tienen muchos hijos…"* is `conversaciones.94` verbatim; `ecp.94` is the close of the Holy Thursday meditation.
- `(F, 420)` in `examen-de-conciencia.es.md` — *"cuando se ama de veras..., siempre se encuentran detalles para amar todavía más"* is `surco.420`; `forja.420` is on divine filiation and perseverance.
- `(ECP, 148)` in `humildad.es.md` — a 133-word quotation, *"Al comportarnos con normalidad -como nuestros iguales- y con sentido sobrenatural…"*, is `ad.121` word for word; `ecp.148` treats the same theme in different words, which is how the error was made.

## The 26, and the one not located

`voz` is the citing anchor: every row's citing passage is `{#dicsje.<voz>}`.

### Right number, wrong work (8)

| cited | voz | actually |
|---|---|---|
| `(AD, 145)` | `magnanimidad` | `ecp.145` |
| `(C, 737)` | `cosas-pequenas` | `surco.737` |
| `(CONV, 24)` | `matrimonio` | `ecp.24` |
| `(CONV, 26)` | `matrimonio` | `ecp.26` |
| `(ECP, 93)` | `matrimonio` | `conversaciones.93` |
| `(ECP, 94)` | `matrimonio` | `conversaciones.94` |
| `(ECP, 283)` | `vida-interior` | `camino.283` — and ECP has only 187 points |
| `(F, 420)` | `examen-de-conciencia` | `surco.420` |

### Wrong number, right work (15)

| cited | voz | actually |
|---|---|---|
| `(AD, 27)` | `templanza` | `ad.26` |
| `(AD, 111)` | `identificacion-con-cristo` | `ad.110` |
| `(AD, 138)` | `penitencia-virtud-y-sacramento-de-la` | `ad.139` |
| `(AD, 227)` | `maria-santisima-devocion-a` | `ad.277` |
| `(AD, 295)` | `amigos-de-dios-libro` | `ad.205` |
| `(C, 57)` | `espiritu-santo` | `camino.638` — the *second* `(C, 57)` in the same paragraph is correct |
| `(C, 616)` | `obediencia` | `camino.614` |
| `(C, 720)` | `jaculatorias` | `camino.729` |
| `(C, 782)` | `jaculatorias` | `camino.762` |
| `(CONV, 20)` | `iglesia` | `conversaciones.21` |
| `(CONV, 21)` | `vida-ordinaria-santificacion-de-la` | `conversaciones.58` |
| `(CONV, 65)` | `iglesia` | `conversaciones.66` |
| `(ECP, 17)` | `filiacion-divina` | `ecp.65` |
| `(ECP, 40)` | `maria-santisima-devocion-a` | `ecp.140` |
| `(ECP, 43)` | `fe` | `ecp.42` |

### Wrong work and number (3)

| cited | voz | actually |
|---|---|---|
| `(ECP, 98)` | `maria-santisima-devocion-a` | `ad.74` |
| `(ECP, 148)` | `humildad` | `ad.121` |
| `(ECP, 213)` | `penitencia-virtud-y-sacramento-de-la` | `ad.214` — and ECP has only 187 points |

### Not located (1)

`(CONV, 113)` in `vida-ordinaria-santificacion-de-la` quotes *«verdadero lugar de la existencia secular cristiana»*, introduced as St Josemaría's *"términos definitorios"*. The phrase occurs nowhere in the six works, nor anywhere else in `01. Sources/San Josemaria/`. It reads as the *Diccionario*'s own summary formula set in quotation marks. **Left unresolved, which is the correct state.** The second `(CONV, 113)` in the same voz, quoting the Navarra homily, is correct.

## Two the checker got wrong, and they are recorded because it matters

Two of the 29 raw failures were **the instrument's fault, not the *Diccionario*'s**, and were caught only by opening them:

- `(ECP, 178)` in `humildad` scored 0.39 because the *Diccionario* prefixes a Latin tag from elsewhere to the ECP sentence. The sentence itself — *"la mayor humildad se conjuga con la mayor gloria"* — is `ecp.178f`, exactly where it is cited. **A partial reading of a long point read as a wrong reference.**
- `(F, 562)` in `fraternidad` quotes *«ser alfombra para que los demás pisen blando»*; `forja.562` reads *"hay que hacerse alfombra en donde los demás pisen blando"*. The *Diccionario*'s own prose announces it — *"enseñaba san Josemaría con una imagen plástica"*. **A paraphrase inside quotation marks, correctly referenced.**

Neither is in the 26.

## Method

`04. Reference/anchors.md` mappings: `C`→`camino` (999 points), `S`→`surco` (1000), `F`→`forja` (1055), `ECP`→`ecp` (187), `AD`→`ad` (316), `CONV`→`conversaciones` (123) — anchor counts read off the files, and each matches the work's known length.

An anchor's body is everything between `{#sigla.N}` and the next `{#sigla.M}`, so sub-anchors (`ecp.17a`…`17h`, `ad.121b`) sit inside their point. A citation is a closing quote immediately followed by `(ABBR, refs)`; `cfr.` is excluded; the quotation is taken by delimiter parity inside its paragraph, never by scanning backwards past a paragraph. Both sides are tokenised — lowercased, diacritics stripped, markdown and anchor syntax removed, **bare digit runs dropped** (footnote markers), punctuation dropped. A quotation matches if ≥ 60 % of its tokens fall inside `difflib` matching runs of ≥ 2 tokens against the **concatenation of every anchor named in the parenthesis**. Elisions `(...)`, substituted words and the *Diccionario*'s own typos cost a run, not the whole match.

**The measure is not sensitive to its settings**: run ≥ 3 / 60 % gives 33 mismatches, run ≥ 2 / 70 % gives 30, run ≥ 2 / 60 % gives 27. Every one of the 27 was then located across all six works and read by hand.

## What is still open

- **The 26 are not corrected in the files, and should not be silently corrected.** They are the printed work's errors, and the *Diccionario* is a source. If the citing passages are ever to carry a resolved link, the honest form is a sidecar — this file — not an edit to the text.
- **`(CONV, 113)`** is unresolved and stays so.
- **43 citations are too short to test** (quotations under three words). They are not counted either way.
- **This tests six works only.** The *Diccionario* also cites `LG`, `GS`, `ChL`, `S.Th.`, `AAS` and some forty modern authors; none of those is tested here.
