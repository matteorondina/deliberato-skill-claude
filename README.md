# Deliberato

*Il council decisionale in italiano per founder e PMI.*

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Lingua: Italiano](https://img.shields.io/badge/Lingua-Italiano-blue.svg)](README.md)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)](https://github.com/matteorondina/deliberato)

---

Deliberato è una Claude Skill che convoca un council di 4 advisor AI specializzati per analizzare decisioni strategiche complesse. Ogni advisor guarda la decisione da un angolo diverso, si rivedono a vicenda in anonimo, un chairman sintetizza il verdetto con raccomandazione e piano d'azione.

Pensato per founder e PMI italiane che affrontano decisioni strategiche senza un board di consulenti fisici.

---

## Quick start

**1. Installa**

Apri Claude e incolla:

```
Installa la skill da questo repository GitHub: https://github.com/matteorondina/deliberato
```

In alternativa, scarica `SKILL.md` e incollalo in Claude chiedendo di installarlo come skill.

**2. Usa**

```
"Delibera questa decisione: [descrizione]"
"Convoca il council: devo decidere se [A] o [B]"
"Passa al council: vale la pena [iniziativa]?"
"Council questa decisione: [descrizione]"
```

---

## Come funziona

**Intake** — 5 domande strutturate per inquadrare la decisione, specifiche per modalità.

**4 advisor in parallelo** — ognuno analizza dalla propria prospettiva (200-300 parole ciascuno, senza preamboli). Il parallelo è obbligatorio: previene il bias di chi parla per primo.

**Peer review anonima** — le risposte vengono randomizzate e anonimizzate (A/B/C/D). Ogni advisor revisiona le risposte degli altri senza sapere chi le ha scritte, rispondendo a 3 domande: risposta più forte, blind spot più grande, cosa mancano tutte e quattro.

**Chairman synthesis** — un agente sintetizza advisor e review in un verdetto strutturato con: punti di accordo, disaccordi genuini, blind spot emersi, raccomandazione, confidence qualificata, piano d'azione a 24h / 7gg / 30gg.

---

## Modalità disponibili

| Modalità | Advisor | Per cosa |
|---|---|---|
| **Marketing & AI Strategy** | Lo Stratega di Prodotto, L'Economista Pragmatico, Il Realista Operativo, Il Contrarian AI-aware | Strategia marketing, stack AI, build vs buy, prioritizzazione iniziative, posizionamento |
| **Pricing** | Lo Stratega del Valore, L'Analista di Unit Economics, Il Comportamentalista, Il Realista di Mercato | Modello di prezzo, freemium vs paid, aumento prezzi, cambio modello di ricavo |
| **Hiring e Team** | Lo Stratega del Team, Il Numerico, Il Costruttore di Cultura, Il Pragmatico Giuslavoristico | Primo dipendente, assunzione vs freelance, generalista vs specialista, in-house vs esternalizzare |
| **Direzione Strategica** | L'Analista dei Segnali, Il Guardiano del Focus, Il Costruttore di Moat, Il Realista delle Persone | Pivot parziale o totale, abbandono feature o prodotto, nuovo segmento, cambio cliente target |

---

## Roadmap

**In sviluppo (Fase 2)**

| Cluster | Decisioni |
|---|---|
| Partnership e distribuzione | Esclusiva vs non esclusiva, canale diretto vs marketplace |
| Capitali e finanza | Bootstrap vs round, valutare un'offerta di investimento |

Filosofia: una sola skill che cresce nel tempo, non una proliferazione di skill separate.

---

## Esempio di sessione

[`examples/esempio-stack-ai-mvp.md`](examples/esempio-stack-ai-mvp.md) — una PMI di consulenza HR valuta se costruire internamente un agente AI per lo screening CV o acquistare un SaaS verticale. Caso realistico con GDPR, AI Act, vincoli di budget e team. Mostra l'intera sessione: intake, 4 risposte advisor, 4 peer review, verdetto finale.

---

## Confronto con LLM Council

| | LLM Council | Deliberato |
|---|---|---|
| Lingua e contesto | Inglese, esempi USA | Italiano, esempi PMI e founder italiane |
| Modalità | Una sola, generalista | Multi-modalità (2 attive, altre in roadmap) |
| Intake | Veloce, ~1 domanda | Strutturato, 5 domande mirate per modalità |
| Advisor | 5 fissi (thinking lenses) | 4 specializzati per modalità |
| Guardrail | Non trattati | GDPR/AI Act, lock-in strategico, debito tecnico, unit economics, WTP |
| Output | Verdetto + 1 next step | Stesso impianto + confidence qualificata + piano 24h/7gg/30gg |

---

## Crediti e ispirazione

Deliberato si ispira al pattern *LLM Council* di [Ole Lehmann](https://github.com/aiwithremy/claude-skills-llm-council), basato sulla metodologia *LLM Council* di [Andrej Karpathy](https://github.com/karpathy/llm-council). Riconosco l'intuizione originale e ringrazio gli autori per il contributo all'ecosistema delle Claude Skills.

Deliberato è un progetto indipendente, scritto da zero in italiano, con advisor specializzati, intake strutturato e guardrail compliance per il contesto UE.

## Disclaimer

Deliberato è uno strumento di supporto alla decisione. Non sostituisce consulenza legale, finanziaria, fiscale o medica specialistica. Per aspetti di compliance (GDPR, AI Act) consultare professionisti qualificati. La decisione finale resta dell'utente.

## Licenza e autore

MIT — [Matteo Rondina](https://www.linkedin.com/in/matteorondina/)
