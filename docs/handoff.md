# Handoff — Deliberato

Data: 2026-06-03

---

## Cos'è Deliberato

Claude Skill in italiano per decisioni strategiche di business. Convoca un council di advisor AI specializzati, peer review anonima, sintesi del chairman con raccomandazione e piano d'azione. Pensata per founder, manager e professionisti italiani.

Repository: `https://github.com/matteorondina/deliberato`
Branch principale: `main`
Branch di sviluppo attivo: `claude/deliberato-skill-setup-Bqy0u`

---

## Stato attuale del repo

```
SKILL.md                              — entry point della skill, flusso completo
modes/
  marketing-ai-strategy.md
  pricing.md
  hiring.md
  direzione-strategica.md
  partnership-distribuzione.md
  capitali-finanza.md
examples/
  esempio-stack-ai-mvp.md            — Full Council (HR, build vs buy AI)
  esempio-pricing-fast-council.md    — Fast Council (SaaS, aumento prezzi)
docs/
  design-handoff.md                  — brief per designer del sito
  handoff.md                         — questo file
README.md
LICENSE                              — MIT, Matteo Rondina
.gitignore                           — esclude transcript-deliberato-*.md e active/
```

---

## Architettura della skill

### Due velocità

| | Full Council | Fast Council |
|---|---|---|
| Trigger | "delibera questa decisione", "convoca il council", "stresstest questa scelta"… | "check questa decisione", "parere rapido", "analisi rapida"… |
| Advisor | 5 in parallelo | 3 in parallelo (primi 3 del file modalità) |
| Peer review | Sì — 5 reviewer anonimi (A/B/C/D/E) | No |
| Chairman | Verdetto completo + piano 24h/7gg/30gg | Verdetto compatto + 1 azione in 24h |
| LLM calls | ~11 | ~4 |

### 6 modalità

| Modalità | File | Advisor 1-2-3 (fast) | Advisor 4-5 (solo full) |
|---|---|---|---|
| Marketing & AI Strategy | `modes/marketing-ai-strategy.md` | Lo Stratega di Prodotto, L'Economista Pragmatico, Il Realista Operativo | Il Contrarian AI-aware, L'Espansore |
| Pricing | `modes/pricing.md` | Lo Stratega del Valore, L'Analista di Unit Economics, Il Comportamentalista | Il Realista di Mercato, Il Provocatore |
| Hiring e Team | `modes/hiring.md` | Lo Stratega del Team, Il Numerico, Il Costruttore di Cultura | Il Pragmatico Giuslavoristico, Il Questionatore |
| Direzione Strategica | `modes/direzione-strategica.md` | L'Analista dei Segnali, Il Guardiano del Focus, Il Costruttore di Moat | Il Realista delle Persone, L'Amplificatore |
| Partnership e Distribuzione | `modes/partnership-distribuzione.md` | Lo Stratega del Canale, Il Negoziatore, Il Realista delle Dipendenze | L'Economista della Distribuzione, Il Laterale |
| Capitali e Finanza | `modes/capitali-finanza.md` | Il Custode della Missione, Il Matematico del Capitale, Il Conoscitore di Investitori | Il Realista del Mercato Italiano, Il Visionario |

### 5° advisor per modalità (Espansore/Outsider)
Ogni modalità ha un 5° advisor che sfida il framing della decisione dall'esterno — ispirato ai concetti Expansionist + Outsider di LLM Council. Entra solo nel Full Council.

### Meccanismi speciali
- **`## Istruzioni per il chairman`** — sezione opzionale nei file modalità. Se presente, il chairman la applica dopo la struttura standard. Implementata in `capitali-finanza.md` (disclaimer legale/fiscale rafforzato).
- **Guardrail nei prompt template** — ogni advisor ha guardrail specifici embedded nel proprio prompt (non solo nelle note a fondo file). GDPR/AI Act → Il Contrarian. Debito tecnico → Il Realista Operativo. Costo opportunità → L'Economista Pragmatico. Ecc.
- **Transcript opzionale** — se l'utente chiede di salvare, il file viene scritto come `transcript-deliberato-YYYYMMDD-HHmm.md` (escluso da `.gitignore`).

---

## Decisioni di prodotto prese

**Cosa fare / già fatto:**
- 5 advisor per modalità (non 4, non 6)
- Fast Council come flusso alternativo nello stesso file SKILL.md, non skill separata
- Posizionamento: "founder, manager e professionisti italiani" — non "founder e PMI" (troppo stretto) né "chiunque" (troppo generico)
- Nessuna modalità "AI" separata — già coperta orizzontalmente
- Nessuna modalità "Go-to-market" per ora — unica che potrebbe valere, ma dopo feedback d'uso

**Cosa NON fare:**
- Non proliferare skill separate per topic — una skill che cresce
- Non togliere il focus italiano — è il moat (CCNL, GDPR, PNRR, AI Act UE)
- Non aggiungere modalità finché non c'è feedback dal sito

---

## Prossimo step: il sito

### Struttura
Due pagine:
1. **Home** — il tool: textarea per la decisione, toggle Full/Fast, output in streaming con card advisor + verdetto chairman
2. **Come funziona** — one-pager condivisibile: problema, processo, due velocità, 6 modalità, perché italiano, CTA

### Brief completo
→ `docs/design-handoff.md`

### Stack suggerito
- Next.js + Vercel (deploy semplice)
- Anthropic SDK (chiamate API dirette)
- Supabase opzionale (se vuoi storico sessioni / auth)

### Costo per sessione (stima)
- Full Council: ~€0,10–0,20 a sessione (claude-sonnet-4-6, ~11 chiamate, ~10-15k token totali)
- Fast Council: ~€0,04–0,08 a sessione (~4 chiamate)
- Con 100 utenti/giorno full: ~€300–600/mese solo API

### Decisione da prendere prima di costruire
Modello economico: gratuito (paghi tu), freemium (fast gratis / full a pagamento), o subscription. Condiziona tutta l'architettura.

---

## Setup locale

```bash
# Clona il repo
mkdir -p ~/projects && git clone https://github.com/matteorondina/deliberato ~/projects/deliberato

# Entra e attiva il branch di sviluppo
cd ~/projects/deliberato
git checkout claude/deliberato-skill-setup-Bqy0u
```

---

## Come installare e testare la skill

1. Apri Claude (claude.ai o app desktop)
2. Vai in Settings → Skills → Add skill
3. Incolla il contenuto di `SKILL.md` oppure usa: `Installa la skill da questo repository GitHub: https://github.com/matteorondina/deliberato`
4. Testa con: `"Check questa decisione: [qualcosa di concreto]"` (Fast Council) o `"Delibera questa decisione: [qualcosa]"` (Full Council)
