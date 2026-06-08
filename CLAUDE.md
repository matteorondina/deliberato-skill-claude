# CLAUDE.md — Deliberato

Contesto tecnico del repo. Complementare al CLAUDE.md globale, non lo duplica.

## Cos'è

Claude Skill in italiano per decisioni strategiche di business. Convoca un council di advisor AI specializzati, esegue peer review anonima, e produce una sintesi del chairman con raccomandazione e piano d'azione. Target: founder, manager e professionisti italiani.

- Repo: `github.com/matteorondina/deliberato-skill-claude` (cartella locale: `deliberatoskill`)
- Branch principale: `main`
- Branch di sviluppo: `claude/deliberato-skill-setup-Bqy0u`
- Licenza: MIT (Matteo Rondina)

## Struttura repo

```
SKILL.md                              entry point, frontmatter con trigger + flusso completo
modes/                                una modalità per file
  marketing-ai-strategy.md
  pricing.md
  hiring.md
  direzione-strategica.md
  partnership-distribuzione.md
  capitali-finanza.md
examples/
  esempio-stack-ai-mvp.md             esempio Full Council (HR, build vs buy AI)
  esempio-pricing-fast-council.md     esempio Fast Council (SaaS, aumento prezzi)
assets/                               immagini per il README (og-image.png, icon-512.png)
README.md
LICENSE
.gitignore                            esclude transcript-deliberato-*.md e active/
```

## Architettura a due velocità

| | Full Council | Fast Council |
|---|---|---|
| Trigger | "delibera questa decisione", "convoca il council", "stresstest questa scelta"… | "check questa decisione", "parere rapido", "analisi rapida"… |
| Advisor | 5 in parallelo | 3 in parallelo (i primi 3 del file modalità) |
| Peer review | Sì — 5 reviewer anonimi (A/B/C/D/E) | No |
| Chairman | Verdetto completo + piano 24h/7gg/30gg | Verdetto compatto + 1 azione in 24h |
| Chiamate LLM | ~11 | ~4 |

Fast Council è un flusso alternativo nello **stesso** `SKILL.md`, non una skill separata.

## 6 modalità

| Modalità | File | Advisor 1-2-3 (anche Fast) | Advisor 4-5 (solo Full) |
|---|---|---|---|
| Marketing & AI Strategy | `modes/marketing-ai-strategy.md` | Stratega di Prodotto, Economista Pragmatico, Realista Operativo | Contrarian AI-aware, Espansore |
| Pricing | `modes/pricing.md` | Stratega del Valore, Analista di Unit Economics, Comportamentalista | Realista di Mercato, Provocatore |
| Hiring e Team | `modes/hiring.md` | Stratega del Team, Numerico, Costruttore di Cultura | Pragmatico Giuslavoristico, Questionatore |
| Direzione Strategica | `modes/direzione-strategica.md` | Analista dei Segnali, Guardiano del Focus, Costruttore di Moat | Realista delle Persone, Amplificatore |
| Partnership e Distribuzione | `modes/partnership-distribuzione.md` | Stratega del Canale, Negoziatore, Realista delle Dipendenze | Economista della Distribuzione, Laterale |
| Capitali e Finanza | `modes/capitali-finanza.md` | Custode della Missione, Matematico del Capitale, Conoscitore di Investitori | Realista del Mercato Italiano, Visionario |

Il 5° advisor di ogni modalità (Espansore/Outsider) sfida il framing della decisione dall'esterno (ispirato ai concetti Expansionist + Outsider di LLM Council). Entra solo nel Full Council.

## Meccanismi speciali

- **`## Istruzioni per il chairman`** — sezione opzionale nei file modalità. Se presente, il chairman la applica dopo la struttura standard. Implementata in `capitali-finanza.md` (disclaimer legale/fiscale rafforzato).
- **Guardrail nei prompt template** — ogni advisor ha guardrail specifici embedded nel proprio prompt, non solo nelle note a fondo file. Es: GDPR/AI Act → Il Contrarian; debito tecnico → Il Realista Operativo; costo opportunità → L'Economista Pragmatico.
- **Transcript opzionale** — su richiesta dell'utente, la sessione viene salvata come `transcript-deliberato-YYYYMMDD-HHmm.md` (escluso da `.gitignore`).
- **Limiti di output per il budget di risposta** — advisor max 120 parole (non 200-300), reviewer max 100 parole (non 200). La peer review occupa ~500 parole (5 × 100), gli advisor ~600 (5 × 120), il chairman ~300: totale ~1.400 parole, entro il budget di output. `<details>/<summary>` HTML non funziona in Claude.ai (solo markdown), quindi non è una soluzione percorribile per ridurre l'output visibile.
- **Guard intake** — prima di avviare il council (Step 2 Full e FC-Step 2 Fast), l'orchestratore verifica: (1) trade-off genuino tra almeno due opzioni con costi reali, (2) perimetro professionale/business. Se manca una condizione, chiede conferma esplicita all'utente prima di procedere.

## Decisioni di prodotto ferme

- 5 advisor per modalità (non 4, non 6).
- Una skill che cresce, non proliferazione di skill separate per topic.
- Posizionamento "founder, manager e professionisti italiani" — non "founder e PMI" (troppo stretto) né "chiunque" (troppo generico).
- Niente modalità "AI" separata (coperta orizzontalmente). Niente "Go-to-market" per ora (solo dopo feedback d'uso).
- Focus italiano come moat (CCNL, GDPR, PNRR, AI Act UE): non togliere.
- Non aggiungere modalità finché non c'è feedback dal sito.
- La skill è per decisioni professionali/business (le 6 modalità). Decisioni personali o familiari non rientrano nel perimetro — il guard all'intake lo segnala esplicitamente.

## Il sito (repo gemello `deliberatosite`)

Il sito è costruito e in produzione su Vercel: repo `deliberatosite`
(Next.js 16), con il council reale via `/api/council`. Modello economico
deciso: reale ma protetto, gratuito con tetto anti-abuso (no auth/pagamenti).

I `modes/*.md` di questo repo sono la **fonte di verità unica dei prompt**:
il sito li rigenera in `lib/prompts.generated.ts` con `npm run gen:prompts`.
Se modifichi un prompt advisor qui, rigenera lato sito.
