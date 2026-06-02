# Design Brief — Deliberato

## Prodotto

Deliberato è una Claude Skill italiana che aiuta founder e PMI a prendere decisioni strategiche complesse. Convoca un council di advisor AI specializzati, ognuno con un angolo diverso. Esiste in due velocità: **Full Council** (5 advisor + peer review anonima + chairman) e **Fast Council** (3 advisor + chairman diretto).

Il contesto italiano è il differenziatore principale: guardrail su GDPR, AI Act, diritto del lavoro italiano, mercato VC italiano. Non è un tool generico in inglese.

---

## Tono e identità visiva

- **Pubblico**: founder e imprenditori italiani, 30–45 anni, abituati a tool professionali
- **Tono**: serio, diretto, professionale. Non startup-y, non corporate. Pensa a uno studio legale moderno che usa tecnologia, non a una SaaS americana
- **Lingua**: italiano in tutto il copy
- **No a**: emoji, colori sgargianti, animazioni distraenti, tono "rivoluzionario"
- **Sì a**: gerarchia chiara, spazio bianco, tipografia leggibile, un colore primario forte con neutral come sfondo

---

## Struttura del sito: 2 pagine

---

### Pagina 1 — Home: il tool

**Obiettivo**: l'utente arriva, capisce in 5 secondi cosa fa, inserisce la sua decisione e parte.

**Layout dall'alto verso il basso:**

**1. Header minimale**
- Logo/nome "Deliberato"
- Link alla pagina "Come funziona"

**2. Hero**
- Headline: *"Il tuo board di advisor AI. In italiano."* (o variante: *"Porta la tua decisione al council."*)
- Sub: 1 riga su cosa fa — niente paragrafi
- Nessun CTA separato: il form è già il CTA

**3. Il form centrale** — è il cuore della pagina
- Textarea grande: placeholder *"Descrivi la decisione che devi prendere"*
- Toggle o scelta visiva: **Full Council** / **Fast Council**
  - Full Council: analisi completa — 5 advisor, peer review anonima, ~5 min
  - Fast Council: parere rapido — 3 advisor, chairman diretto, ~1 min
- Bottone primario: *"Convoca il council"*

**4. Output area** (appare dopo submit, sostituisce o si aggiunge sotto il form)
- Mostra il processo in sequenza visibile:
  1. Identificazione modalità
  2. Advisor in parallelo (card affiancate, contenuto in streaming)
  3. Peer review — solo Full Council
  4. Verdetto del chairman (separato visivamente, in evidenza)
- Gli advisor appaiono come card affiancate con nome e testo in streaming
- Il verdetto finale ha gerarchia visiva più alta rispetto alle card advisor

**5. Footer minimale**
- Link a GitHub del progetto
- Disclaimer legale in piccolo
- Autore: Matteo Rondina

---

### Pagina 2 — Come funziona (one-pager)

**Obiettivo**: convincere chi non conosce ancora Deliberato. Pensata per essere condivisa su LinkedIn, newsletter, community di founder.

**Sezioni:**

**1. Hero**
- Headline: *"Prendi decisioni strategiche da solo. Ma non in modo solitario."* (o variante da testare)
- Sub: 2 righe su cosa è Deliberato
- CTA: *"Prova il council →"* (link alla home)

**2. Il problema**
- 3–4 righe. I founder italiani prendono decisioni critiche senza un board reale. Le consulenze costano, gli amici non hanno il contesto, i tool AI generalisti non hanno guardrail per il contesto italiano.

**3. Come funziona**
- Visualizzazione del processo in 4 step (icone o numerazione verticale/orizzontale):
  1. Descrivi la tua decisione
  2. Il council si convoca — gli advisor analizzano in parallelo
  3. Peer review anonima — ogni advisor revisiona gli altri senza sapere chi ha scritto cosa
  4. Il chairman sintetizza il verdetto con raccomandazione, confidence e piano d'azione

**4. Le due velocità**
- Due card affiancate: Full Council / Fast Council
- Tabella comparativa per ciascuna: numero advisor, peer review sì/no, tempo stimato, quando usarlo

| | Full Council | Fast Council |
|---|---|---|
| Advisor | 5 in parallelo | 3 in parallelo |
| Peer review | Sì, anonima | No |
| Tempo stimato | ~5 minuti | ~1 minuto |
| Quando usarlo | Decisioni irreversibili, alto impatto | Decisioni importanti ma correggibili |

**5. Le 6 modalità**
- 6 card o righe con: nome modalità + descrizione 1 riga + advisor principali

| Modalità | Per cosa | Advisor chiave |
|---|---|---|
| Marketing & AI Strategy | Stack AI, build vs buy, posizionamento | Lo Stratega di Prodotto, Il Contrarian AI-aware |
| Pricing | Modello di prezzo, freemium, aumento prezzi | L'Analista di Unit Economics, Il Comportamentalista |
| Hiring e Team | Primo dipendente, assunzione vs freelance | Il Pragmatico Giuslavoristico, Il Numerico |
| Direzione Strategica | Pivot, abbandono feature, nuovo segmento | L'Analista dei Segnali, Il Costruttore di Moat |
| Partnership e Distribuzione | Esclusiva, marketplace, white-label | Il Negoziatore, Il Realista delle Dipendenze |
| Capitali e Finanza | Bootstrap vs round, valutare un term sheet | Il Matematico del Capitale, Il Realista del Mercato Italiano |

**6. Perché italiano**
- Sezione breve (3–4 righe + eventuali bullet) sul differenziatore concreto:
  - Guardrail GDPR e AI Act nei prompt degli advisor
  - Contesto giuslavoristico italiano (CCNL, periodo di prova, costi di uscita)
  - Ecosistema VC italiano (PNRR, Invitalia, CDP, bandi regionali)
  - Esempi e casi d'uso calibrati su PMI e founder italiani, non su startup americane

**7. CTA finale**
- Headline: *"Porta la tua prossima decisione al council"*
- Bottone primario: *"Inizia gratis →"*

**8. Footer**
- Link a GitHub
- Autore: Matteo Rondina — link LinkedIn
- Disclaimer: *"Deliberato è uno strumento di supporto alla decisione. Non sostituisce consulenza legale, finanziaria o fiscale specialistica."*
- Licenza MIT

---

## Specifiche tecniche

- **Output atteso**: HTML/CSS statico per il one-pager; design in Figma o file esportabile se si parte dal design
- **Responsive**: sì, mobile-first
- **Breakpoint principali**: 375px (mobile), 768px (tablet), 1280px (desktop)
- **Font**: famiglia serif moderna (per autorevolezza) o sans-serif geometrica pulita — no Google Fonts generici tipo Roboto o Open Sans
- **Il form della home** è il componente più importante dell'intera interfaccia — deve essere grande, centrato, invitante. Non deve intimidire.
- **L'output area** (risultato del council) non va progettata nel dettaglio — è markdown renderizzato. Serve uno stile pulito per titoli, paragrafi, liste. Le card advisor hanno tutte la stessa struttura: nome advisor + testo.
- **Streaming**: il testo degli advisor appare progressivamente (carattere per carattere o per blocchi). Il design deve reggere contenuto parziale senza sembrare rotto.

---

## Riferimenti di stile (opzionali)

Tono visivo di riferimento: tool professionali italiani o europei con interfaccia pulita e copy diretto. Evitare riferimenti a SaaS americane con stile "landing page da growth hacker".
