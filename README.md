<p align="center">
  <img src="assets/og-image.png" alt="Deliberato — il council decisionale in italiano" width="640">
</p>

# Deliberato

*Il council decisionale in italiano per founder, manager e professionisti.*

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Lingua: Italiano](https://img.shields.io/badge/Lingua-Italiano-blue.svg)](README.md)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)](https://github.com/matteorondina/deliberato-skill-claude)

---

Deliberato è una Claude Skill che convoca un council di advisor AI specializzati per analizzare decisioni strategiche complesse. Esiste in due velocità: **Full Council** (5 advisor + peer review anonima) per decisioni critiche, **Fast Council** (3 advisor, chairman diretto) per decisioni importanti che non richiedono il processo completo. Un chairman sintetizza il verdetto con raccomandazione e piano d'azione.

Pensato per founder, manager e professionisti italiani che affrontano decisioni strategiche di business senza un board di consulenti fisici.

---

## Quick start

**1. Installa**

Apri Claude e incolla:

```
Installa la skill da questo repository GitHub: https://github.com/matteorondina/deliberato-skill-claude
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

**Rilasciato:**
- 6 modalità specializzate con 5 advisor ciascuna (Marketing & AI Strategy, Pricing, Hiring e Team, Direzione Strategica, Partnership e Distribuzione, Capitali e Finanza)
- Fast Council — flusso rapido con 3 advisor e chairman diretto, senza peer review (~4 chiamate LLM)
- Prospettiva espansore integrata in ogni modalità (5° advisor che sfida il framing della decisione)

**In lavorazione:**
- Sito web Deliberato — interfaccia pubblica per usare il council senza installare la skill

Filosofia: una sola skill che cresce nel tempo, non una proliferazione di skill separate.

---

## Esempi di sessione

[`examples/esempio-stack-ai-mvp.md`](examples/esempio-stack-ai-mvp.md) — **Full Council.** Una PMI di consulenza HR valuta se costruire internamente un agente AI per lo screening CV o acquistare un SaaS verticale. Caso realistico con GDPR, AI Act, vincoli di budget e team. Intake completo, 5 advisor, 5 peer review, verdetto con piano d'azione.

[`examples/esempio-pricing-fast-council.md`](examples/esempio-pricing-fast-council.md) — **Fast Council.** Un founder SaaS decide se alzare i prezzi del 61% prima o dopo il lancio di una nuova feature. Intake in 2 domande, 3 advisor in parallelo, verdetto diretto con raccomandazione e prossima azione in 24 ore.

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
