# Deliberato

*Il council decisionale in italiano per founder e PMI.*

Quattro advisor AI analizzano la tua decisione da angoli diversi, si rivedono
a vicenda in anonimo, producono un verdetto strutturato con raccomandazione
e piano d'azione.

## Che cos'è

Deliberato è una Claude Skill. Viene attivata all'interno di Claude (claude.ai o Claude Code) e guida l'utente attraverso un processo deliberativo strutturato. Non è un chatbot generico, non risponde a domande factual, non scrive testi. Serve a prendere decisioni strategiche complesse con trade-off reali, dove una risposta diretta non basta e il rischio di bias o punti ciechi è alto.

## A chi serve

Founder di startup italiane, owner di PMI, consulenti e manager che affrontano decisioni strategiche su marketing e AI. Non richiede competenze tecniche per usarla. L'unico prerequisito è avere una decisione reale con opzioni e vincoli chiari da portare al council.

## Come funziona

1. Si attiva tramite frasi trigger (esempi sotto)
2. Intake strutturato: 5 domande per inquadrare la decisione in modo completo
3. 4 advisor analizzano in parallelo dalla loro prospettiva (200-300 parole ciascuno)
4. Peer review anonima: ogni advisor revisiona le risposte degli altri senza sapere chi le ha scritte
5. Chairman synthesis: un agente sintetizza advisor e review in un verdetto strutturato
6. Il verdetto appare in chat in markdown, con raccomandazione e piano d'azione a 24h/7gg/30gg

## Modalità disponibili

| Modalità | Stato | Per cosa |
|---|---|---|
| Marketing & AI Strategy | Attiva | Strategia marketing, stack AI, build vs buy, prioritizzazione iniziative, posizionamento |

*Altre modalità sono in roadmap. Vedi la sezione Roadmap.*

## Differenze rispetto a LLM Council

| | LLM Council | Deliberato |
|---|---|---|
| Lingua e contesto | Inglese, esempi USA | Italiano, esempi PMI e founder italiane |
| Modalità | Una sola, generalista | Multi-modalità (Fase 1: una attiva, altre in roadmap) |
| Intake | Veloce, ~1 domanda di chiarimento | Strutturato, 5 domande mirate per modalità |
| Advisor | 5 fissi (thinking lenses) | 4 specializzati per modalità |
| Compliance UE | Non trattata | Guardrail GDPR/AI Act integrati |
| Output | Verdetto + 1 next step | Stesso impianto + confidence qualificata + piano 24h/7gg/30gg |

## Come si installa

**Opzione 1 — Chiedi a Claude di installarla** (più semplice)

Apri una conversazione con Claude e incolla questo messaggio:

```
Installa la skill da questo repository GitHub: https://github.com/matteorondina/deliberato
```

**Opzione 2 — Scarica SKILL.md**

Scarica il file `SKILL.md` da questo repository e incollalo in una conversazione con Claude chiedendo di installarlo come skill.

## Come si usa

Dopo l'installazione, frasi che attivano Deliberato:

- `"Delibera questa decisione: [descrizione]"`
- `"Convoca il council: devo decidere se [opzione A] o [opzione B]"`
- `"Passa al council: vale la pena [iniziativa]?"`
- `"Council questa decisione: [descrizione]"`

## Esempio di sessione

`examples/esempio-stack-ai-mvp.md` — una PMI di consulenza HR valuta se costruire internamente un agente AI per lo screening CV o acquistare un SaaS verticale. Caso realistico con GDPR, AI Act, vincoli di budget e team. Mostra l'intera sessione: intake, 4 risposte advisor, 4 peer review, verdetto finale.

## Roadmap

**Fase 1 (attuale)** — modalità Marketing & AI Strategy

**Fase 2** — nuove modalità, in ordine di priorità da definire con i feedback:

*Hiring e team*
- Primo dipendente: assunzione vs continuare con freelance
- Generalista vs specialista alla prima assunzione
- Quando assumere in-house vs esternalizzare una funzione

*Pricing e modello di ricavo*
- Freemium vs paid from day 1
- Cambio modello (subscription vs one-time vs usage-based)
- Aumento prezzi su base clienti esistente

*Direzione strategica*
- Quando abbandonare una feature o un prodotto
- Pivot parziale vs totale: quando e come
- Entrare in un nuovo segmento: espansione vs focus

*Partnership e distribuzione*
- Partnership esclusiva vs non esclusiva
- Canale diretto vs marketplace vs rivenditore
- White-label vs branded

*Capitali e finanza*
- Bootstrap vs round di investimento: quando alzare il capitale
- Valutare un'offerta di investimento con condizioni specifiche
- Timing del fundraising rispetto alle metriche attuali

**Fase 3** — modalità in base ai feedback (negoziazione professionale, altre da definire)

Filosofia: una sola skill che cresce nel tempo, non una proliferazione di skill separate.

## Crediti e ispirazione

Deliberato si ispira al pattern *LLM Council* di [Ole Lehmann](https://github.com/aiwithremy/claude-skills-llm-council), basato sulla metodologia *LLM Council* di [Andrej Karpathy](https://github.com/karpathy/llm-council). Riconosco l'intuizione originale e ringrazio gli autori per il contributo all'ecosistema delle Claude Skills.

Deliberato è un progetto indipendente, scritto da zero in italiano, con advisor specializzati, intake strutturato e guardrail compliance per il contesto UE. Pensato per founder e PMI italiane.

## Disclaimer

Deliberato è uno strumento di supporto alla decisione. Non sostituisce consulenza legale, finanziaria, fiscale o medica specialistica. Per aspetti di compliance (GDPR, AI Act) consultare professionisti qualificati. La decisione finale resta dell'utente.

## Licenza

MIT — vedi `LICENSE`.

## Autore

Matteo Rondina — [LinkedIn](https://www.linkedin.com/in/matteorondina/)
