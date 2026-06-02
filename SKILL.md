---
name: deliberato
description: |
  Skill in italiano che aiuta a prendere decisioni strategiche complesse facendole 
  analizzare da 4 advisor AI con prospettive diverse, peer review anonima e 
  sintesi finale del chairman. Pensata per founder e PMI italiane.
  
  TRIGGER PRINCIPALI (sempre attivano): "delibera questa decisione", 
  "convoca il council", "council questa decisione", "fai partire il council", 
  "passa al council", "delibera questa scelta".
  
  TRIGGER CONTESTUALI (attivano solo se c'è una decisione reale con trade-off 
  multipli e stakes significativi): "devo decidere se X o Y", "non so se conviene 
  Z", "vale la pena W", "mi conviene", "che faccio tra A e B".
  
  NON TRIGGERARE su: domande factual ("quanto costa X"), scelte triviali 
  ("uso markdown o no"), richieste di scrittura ("scrivimi una mail"), 
  domande di opinione senza decisione strutturata ("che ne pensi di Y"), 
  task di esecuzione tecnica.
  
  Modalità attive: "Marketing & AI Strategy" (strategia marketing, stack AI, 
  build vs buy, posizionamento), "Pricing" (modello di prezzo, freemium vs 
  paid, aumento prezzi), "Hiring e Team" (primo dipendente, assunzione vs 
  freelance, generalista vs specialista), "Direzione Strategica" (pivot, 
  abbandono feature, nuovo segmento), "Partnership e Distribuzione" (canali, 
  esclusiva, marketplace, white-label), "Capitali e Finanza" (fundraising, 
  bootstrap vs round, valutazione offerte di investimento).
---

# Deliberato

Deliberato convoca un council di 4 advisor AI per analizzare decisioni strategiche complesse. Ogni advisor guarda la decisione da un angolo diverso, si rivedono a vicenda in anonimo, un chairman sintetizza il verdetto. Pensato per founder e PMI italiane che affrontano decisioni strategiche senza un board di consulenti fisici.

## Quando si attiva

### Buone domande per Deliberato

- Scelgo tra costruire internamente uno strumento AI o comprare una soluzione SaaS?
- Vale la pena lanciare questo canale di marketing adesso o aspetto di avere più traction?
- Devo assumere un growth marketer in-house o lavorare con un'agenzia?
- Costruisco l'MVP su questo stack o parto con qualcosa di più semplice?
- Ha senso integrare AI in questo processo del mio servizio o è prematuro?
- Continuo a investire su questo posizionamento o cambio rotta?

### Domande sbagliate per Deliberato

- "Quanto costa OpenAI API?" — domanda factual, non una decisione
- "Scrivimi un'email per il cliente" — task di esecuzione
- "Che ne pensi di Notion?" — opinione generica senza decisione strutturata
- "Usa Supabase o Firebase?" — se non c'è contesto di progetto reale con vincoli veri, non c'è trade-off deliberabile

## Modalità disponibili

| Modalità | File | Quando usarla |
|---|---|---|
| Marketing & AI Strategy | `modes/marketing-ai-strategy.md` | Strategia marketing, stack AI, build vs buy, prioritizzazione iniziative, posizionamento |
| Pricing | `modes/pricing.md` | Modello di prezzo, freemium vs paid, aumento prezzi, cambio modello di ricavo |
| Hiring e Team | `modes/hiring.md` | Primo dipendente, assunzione vs freelance, generalista vs specialista, in-house vs esternalizzare |
| Direzione Strategica | `modes/direzione-strategica.md` | Pivot parziale o totale, abbandono feature o prodotto, nuovo segmento, cambio cliente target |
| Partnership e Distribuzione | `modes/partnership-distribuzione.md` | Esclusiva vs non esclusiva, canale diretto vs marketplace vs rivenditore, white-label, accordi di distribuzione |
| Capitali e Finanza | `modes/capitali-finanza.md` | Bootstrap vs round, valutare un'offerta di investimento, scegliere tra investitori, timing del fundraising |

## Il flusso di una sessione

### Step 1 — Identificazione modalità

Quando la skill si attiva, l'orchestratore identifica la modalità appropriata in base alla natura della decisione:

- Se la decisione riguarda strategia marketing, stack tecnologico, build vs buy, posizionamento → **Marketing & AI Strategy**
- Se la decisione riguarda prezzo, modello di ricavo, freemium, aumento prezzi → **Pricing**
- Se la decisione riguarda assunzioni, composizione del team, freelance vs dipendente → **Hiring e Team**
- Se la decisione riguarda cambiamento di direzione, pivot, abbandono di feature o prodotto, nuovo segmento → **Direzione Strategica**
- Se la decisione riguarda partnership, canali di distribuzione, esclusiva, marketplace → **Partnership e Distribuzione**
- Se la decisione riguarda raccolta di capitale, valutazione di un'offerta di investimento, bootstrap vs round → **Capitali e Finanza**

Se il contesto non è chiaro, presenta le opzioni all'utente con una riga di descrizione ciascuna e chiedi quale si applica. Una volta identificata la modalità, comunica: *"Avvio Deliberato in modalità [nome modalità]."*

### Step 2 — Intake strutturato

Carica e applica le 5 domande di intake dal file `modes/marketing-ai-strategy.md`. Le domande vengono poste in modo conversazionale, una alla volta o raggruppate se l'utente ha già fornito contesto ricco nel primo messaggio. Se l'utente è già stato esauriente su alcuni punti, l'orchestratore può saltare le domande già coperte, segnalando quali omette e perché.

### Step 3 — Convocazione advisor (4 in parallelo)

Spawna 4 sub-agenti in parallelo, uno per advisor, ognuno con il proprio prompt template (definito nel file della modalità attiva). Ogni advisor produce una risposta di 200-300 parole, in italiano, senza preamboli. Il parallelo è obbligatorio: previene il bias di posizione (chi risponde per primo influenza gli altri).

Prompt template generale per gli advisor:

```
Sei {nome_advisor} in un council deliberativo.

Il tuo stile di pensiero: {descrizione_stile}

Un utente porta al council questa decisione:

---
{brief_inquadrato}
---

Rispondi dalla tua prospettiva. Sii diretto e specifico. Non cercare 
equilibrio, non hedge. Vai a fondo nel tuo angolo di analisi: gli altri 
advisor copriranno gli angoli che tu non copri.

Lunghezza: 200-300 parole. Nessun preambolo, vai dritto all'analisi.
```

### Step 4 — Peer review anonima

Raccogli le 4 risposte degli advisor. Anonimizzale come Risposta A, B, C, D, **randomizzando l'ordine** (così non c'è bias posizionale). Spawna 4 nuovi sub-agenti reviewer in parallelo (uno per advisor): ogni reviewer vede tutte e 4 le risposte anonimizzate e risponde a 3 domande.

Prompt template reviewer:

```
Stai revisionando il lavoro di un council deliberativo. Quattro advisor 
hanno risposto indipendentemente a questa domanda:

---
{brief_inquadrato}
---

Ecco le risposte anonimizzate:

**Risposta A:** {risposta_a}
**Risposta B:** {risposta_b}
**Risposta C:** {risposta_c}
**Risposta D:** {risposta_d}

Rispondi a queste tre domande. Sii specifico. Cita le risposte per lettera.

1. Quale risposta è la più forte? Perché?
2. Quale risposta ha il blind spot più grande? Cosa manca?
3. Cosa hanno mancato TUTTE e quattro le risposte e che il council dovrebbe 
   considerare?

Lunghezza max 200 parole. Sii diretto.
```

### Step 5 — Chairman synthesis

Un singolo agente chairman riceve: il brief, le 4 risposte de-anonimizzate (chi ha detto cosa), le 4 peer review. Produce il verdetto finale nella struttura fissa.

Prompt template chairman:

```
Sei il Chairman di un council deliberativo. Devi sintetizzare il lavoro 
di 4 advisor e delle relative peer review in un verdetto finale.

La decisione portata al council:

---
{brief_inquadrato}
---

RISPOSTE DEGLI ADVISOR:

**{advisor_1_nome}:** {risposta_1}
**{advisor_2_nome}:** {risposta_2}
**{advisor_3_nome}:** {risposta_3}
**{advisor_4_nome}:** {risposta_4}

*(i nomi degli advisor sono quelli definiti nella modalità attiva)*

PEER REVIEW:
{tutte_le_4_review}

Produci il verdetto del council usando ESATTAMENTE questa struttura:

## Verdetto del Council: {topic_breve}

### Dove il council è d'accordo
{punti_di_convergenza}

### Dove il council è in disaccordo
{disaccordi_genuini_con_entrambi_i_lati}

### Blind spot emersi nella revisione
{cose_mancate_dagli_advisor_singoli_e_emerse_in_peer_review}

### La raccomandazione
{raccomandazione_chiara_non_dipende}

### Confidence
ALTA / MEDIA / BASSA — {motivazione_1_2_frasi}

### Piano d'azione
- **Prossime 24 ore:** {una_cosa_concreta}
- **Prossimi 7 giorni:** {1_o_2_cose}
- **Prossimi 30 giorni:** {1_o_2_cose}

---
*Questo verdetto non sostituisce consulenza legale, finanziaria o fiscale 
specialistica. Verificare aspetti compliance (GDPR/AI Act) con specialista 
quando rilevante.*

Sii diretto. Non hedge. Se la maggioranza degli advisor dice una cosa ma 
l'argomento del dissenter è più forte, puoi siderti col dissenter — 
spiegando perché. Il punto del council è dare chiarezza, non equilibrio 
politicamente corretto.
```

### Step 6 — Presentazione in chat

Il verdetto viene presentato direttamente in chat in markdown, senza generare file. Eccezione: se l'utente chiede esplicitamente di salvare il transcript, salva un file `transcript-deliberato-{YYYYMMDD-HHmm}.md` nella cartella corrente (o `./active/` se esiste).

## Note importanti

- Sempre 4 advisor in parallelo, mai sequenziali. La parallelizzazione previene il bias di chi parla per primo.
- Anonimizza sempre le risposte nella peer review. Se i reviewer sanno chi ha scritto cosa, tendono a deferire allo stile più autorevole.
- Il chairman può dissentire dalla maggioranza. Non è un summarizer, è un sintetizzatore con giudizio indipendente.
- Non attivare il council su decisioni triviali. Se l'intake rivela che non c'è un vero trade-off, segnala all'utente e chiedi se vuole comunque procedere.
- I guardrail specifici per modalità (compliance GDPR/AI Act, lock-in strategico, debito tecnico, unit economics, willingness to pay) sono definiti nei rispettivi file modalità e inclusi nei prompt template dei singoli advisor.

## Crediti e ispirazione

Deliberato si ispira al pattern *LLM Council* di Ole Lehmann
(https://github.com/aiwithremy/claude-skills-llm-council), basato sulla
metodologia *LLM Council* di Andrej Karpathy
(https://github.com/karpathy/llm-council).

Deliberato è un progetto indipendente, scritto da zero in italiano, con advisor,
intake e protocolli ridisegnati per founder e PMI italiane e per il contesto UE.
