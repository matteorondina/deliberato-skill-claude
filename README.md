# Deliberato

*Il council decisionale in italiano per founder e PMI.*

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Lingua: Italiano](https://img.shields.io/badge/Lingua-Italiano-blue.svg)](README.md)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)](https://github.com/matteorondina/deliberato)

---

Deliberato è una Claude Skill che convoca un council di advisor AI specializzati per analizzare decisioni strategiche complesse. Esiste in due velocità: **Full Council** (5 advisor + peer review anonima) per decisioni critiche, **Fast Council** (3 advisor, chairman diretto) per decisioni importanti che non richiedono il processo completo. Un chairman sintetizza il verdetto con raccomandazione e piano d'azione.

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

**Full Council** — per decisioni critiche, irreversibili, ad alto impatto:
```
"Delibera questa decisione: [descrizione]"
"Convoca il council: devo decidere se [A] o [B]"
"Passa al council: vale la pena [iniziativa]?"
"Stresstest questa scelta: [descrizione]"
```

**Fast Council** — per decisioni importanti che non richiedono il processo completo:
```
"Check questa decisione: [descrizione]"
"Parere rapido su: [descrizione]"
"Analisi rapida: devo decidere se [A] o [B]"
```

---

## Come funziona

Deliberato opera in due velocità:

| | Full Council | Fast Council |
|---|---|---|
| Advisor | 5 in parallelo | 3 in parallelo |
| Peer review | Sì, anonima | No |
| Chiamate LLM | ~11 | ~4 |
| Quando | Decisioni irreversibili, alto impatto | Decisioni importanti ma correggibili |

**Full Council** — 5 advisor in parallelo analizzano dalla propria prospettiva (200-300 parole ciascuno). Peer review anonima randomizzata (A/B/C/D/E): ogni advisor revisiona gli altri senza sapere chi ha scritto cosa. Chairman synthesis con accordo, disaccordi, blind spot, raccomandazione, confidence, piano 24h / 7gg / 30gg.

**Fast Council** — 3 advisor in parallelo, intake in 2 domande, chairman diretto senza peer review. Verdetto in ~4 chiamate LLM. Alla fine offre sempre il passaggio al Full Council.

---

## Modalità disponibili

| Modalità | Advisor | Per cosa |
|---|---|---|
| **Marketing & AI Strategy** | Lo Stratega di Prodotto, L'Economista Pragmatico, Il Realista Operativo, Il Contrarian AI-aware, L'Espansore | Strategia marketing, stack AI, build vs buy, prioritizzazione iniziative, posizionamento |
| **Pricing** | Lo Stratega del Valore, L'Analista di Unit Economics, Il Comportamentalista, Il Realista di Mercato, Il Provocatore | Modello di prezzo, freemium vs paid, aumento prezzi, cambio modello di ricavo |
| **Hiring e Team** | Lo Stratega del Team, Il Numerico, Il Costruttore di Cultura, Il Pragmatico Giuslavoristico, Il Questionatore | Primo dipendente, assunzione vs freelance, generalista vs specialista, in-house vs esternalizzare |
| **Direzione Strategica** | L'Analista dei Segnali, Il Guardiano del Focus, Il Costruttore di Moat, Il Realista delle Persone, L'Amplificatore | Pivot parziale o totale, abbandono feature o prodotto, nuovo segmento, cambio cliente target |
| **Partnership e Distribuzione** | Lo Stratega del Canale, Il Negoziatore, Il Realista delle Dipendenze, L'Economista della Distribuzione, Il Laterale | Esclusiva vs non esclusiva, canale diretto vs marketplace vs rivenditore, white-label, accordi di distribuzione |
| **Capitali e Finanza** | Il Custode della Missione, Il Matematico del Capitale, Il Conoscitore di Investitori, Il Realista del Mercato Italiano, Il Visionario | Bootstrap vs round, valutare un'offerta di investimento, scegliere tra investitori, timing del fundraising |

---

## Roadmap

Tutte le modalità pianificate sono rilasciate. Le prossime aggiunte verranno definite in base ai feedback d'uso.

Filosofia: una sola skill che cresce nel tempo, non una proliferazione di skill separate.

---

## Esempio di sessione

[`examples/esempio-stack-ai-mvp.md`](examples/esempio-stack-ai-mvp.md) — una PMI di consulenza HR valuta se costruire internamente un agente AI per lo screening CV o acquistare un SaaS verticale. Caso realistico con GDPR, AI Act, vincoli di budget e team. Mostra l'intera sessione Full Council: intake, 5 risposte advisor, 5 peer review, verdetto finale.

---

## Confronto con LLM Council

| | LLM Council | Deliberato |
|---|---|---|
| Lingua e contesto | Inglese, esempi USA | Italiano, esempi PMI e founder italiane |
| Modalità | Una sola, generalista | Multi-modalità (6 attive) |
| Intake | Veloce, ~1 domanda | Strutturato: 5 domande (Full) o 2 domande (Fast) |
| Advisor | 5 fissi (thinking lenses) | 5 specializzati per modalità |
| Guardrail | Non trattati | GDPR/AI Act, lock-in strategico, debito tecnico, unit economics, WTP |
| Output | Verdetto + 1 next step | Full: confidence + piano 24h/7gg/30gg. Fast: confidence + 1 azione immediata |

---

## Crediti e ispirazione

Deliberato si ispira al pattern *LLM Council* di [Ole Lehmann](https://github.com/aiwithremy/claude-skills-llm-council), basato sulla metodologia *LLM Council* di [Andrej Karpathy](https://github.com/karpathy/llm-council). Riconosco l'intuizione originale e ringrazio gli autori per il contributo all'ecosistema delle Claude Skills.

Deliberato è un progetto indipendente, scritto da zero in italiano, con advisor specializzati, intake strutturato e guardrail compliance per il contesto UE.

## Disclaimer

Deliberato è uno strumento di supporto alla decisione. Non sostituisce consulenza legale, finanziaria, fiscale o medica specialistica. Per aspetti di compliance (GDPR, AI Act) consultare professionisti qualificati. La decisione finale resta dell'utente.

## Licenza e autore

MIT — [Matteo Rondina](https://www.linkedin.com/in/matteorondina/)
