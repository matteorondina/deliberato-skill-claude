---
name: deliberato
description: |
  Skill in italiano per decisioni strategiche complesse. Council di advisor AI
  specializzati, peer review anonima, sintesi del chairman. Per founder, manager
  e professionisti italiani. Due velocità: Full Council (5 advisor + peer review) e Fast Council
  (3 advisor, risposta rapida).

  TRIGGER FULL COUNCIL: "delibera questa decisione", "convoca il council",
  "council questa decisione", "fai partire il council", "passa al council",
  "delibera questa scelta", "metti alla prova questa decisione",
  "stresstest questa scelta", "demolisci questa idea",
  "trova i buchi in questo piano".

  TRIGGER FAST COUNCIL: "check questa decisione", "parere rapido",
  "analisi rapida", "check rapido", "quick council", "parere veloce".

  TRIGGER CONTESTUALI (Full Council, solo con decisione reale e trade-off
  significativi): "devo decidere se X o Y", "non so se conviene Z",
  "vale la pena W", "mi conviene", "che faccio tra A e B",
  "sono convinto di fare X ma voglio un contraddittorio",
  "ho già deciso, dimmi dove sbaglio".

  NON TRIGGERARE su: domande factual, scelte triviali, richieste di scrittura,
  opinioni senza decisione strutturata, task di esecuzione tecnica.

  Modalità: Marketing & AI Strategy, Pricing, Hiring e Team, Direzione
  Strategica, Partnership e Distribuzione, Capitali e Finanza.
---

# Deliberato

Deliberato convoca un council di advisor AI per analizzare decisioni strategiche complesse. Esiste in due velocità: **Full Council** (5 advisor, peer review anonima, chairman synthesis — per decisioni critiche) e **Fast Council** (3 advisor, chairman diretto, senza peer review — per decisioni importanti ma non irreversibili). Ogni advisor guarda la decisione da un angolo diverso. Pensato per founder, manager e professionisti italiani che affrontano decisioni strategiche di business senza un board di consulenti fisici.

## Quando si attiva

### Buone domande per Deliberato

Deliberato indirizza automaticamente la domanda alla modalità appropriata.

- Scelgo tra costruire internamente uno strumento AI o comprare una soluzione SaaS?
- Vale la pena lanciare questo canale di marketing adesso o aspetto di avere più traction?
- Assumo il primo dipendente adesso o continuo con i freelance per altri 6 mesi?
- Alzo i prezzi del 30% o lancio un tier premium separato?
- Ha senso fare pivot verso il segmento enterprise o resto sul mid-market?
- Vale la pena accettare questo term sheet o aspetto condizioni migliori?

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

Deliberato opera in due modalità di esecuzione:

| | Full Council | Fast Council |
|---|---|---|
| Trigger | "delibera questa decisione", "convoca il council"… | "check questa decisione", "parere rapido"… |
| Advisor | 5 in parallelo | 3 in parallelo (i primi 3 del file modalità) |
| Peer review | Sì — 5 reviewer anonimi | No |
| Chiamate LLM | ~11 | ~4 |
| Quando usarlo | Decisioni irreversibili, alto impatto, trade-off complessi | Decisioni importanti ma correggibili, quando serve velocità |

Se il trigger è **Fast Council**, vai direttamente alla sezione [Fast Council](#fast-council) in fondo a questo file — salta il flusso qui sotto.

### Step 1 — Identificazione modalità

Quando la skill si attiva, l'orchestratore identifica la modalità appropriata in base alla natura della decisione:

- Se la decisione riguarda strategia marketing, stack tecnologico, build vs buy, posizionamento → **Marketing & AI Strategy**
- Se la decisione riguarda prezzo, modello di ricavo, freemium, aumento prezzi → **Pricing**
- Se la decisione riguarda assunzioni, composizione del team, freelance vs dipendente → **Hiring e Team**
- Se la decisione riguarda cambiamento di direzione, pivot, abbandono di feature o prodotto, nuovo segmento, cambio modello di business, ridefinizione del cliente target → **Direzione Strategica**
- Se la decisione riguarda partnership, canali di distribuzione, esclusiva, marketplace → **Partnership e Distribuzione**
- Se la decisione riguarda raccolta di capitale, valutazione di un'offerta di investimento, bootstrap vs round → **Capitali e Finanza**

Se il contesto non è chiaro, presenta le opzioni all'utente con una riga di descrizione ciascuna e chiedi quale si applica. Una volta identificata la modalità, comunica: *"Avvio Deliberato in modalità [nome modalità]."*

### Step 2 — Intake strutturato

Carica e applica le 5 domande di intake dal file della modalità attiva (percorso indicato nella tabella di questo file, sezione "Modalità disponibili"). Le domande vengono poste in modo conversazionale, una alla volta o raggruppate se l'utente ha già fornito contesto ricco nel primo messaggio. Se l'utente è già stato esauriente su alcuni punti, l'orchestratore può saltare le domande già coperte, segnalando quali omette e perché.

Prima di avviare il council, verifica che la decisione soddisfi entrambe le condizioni:
1. **Trade-off genuino** — esistono almeno due opzioni con vantaggi e costi reali; non c'è una risposta già ovvia o quasi scontata.
2. **Perimetro professionale** — la decisione rientra in una delle 6 modalità (business, strategia aziendale, professionale). Decisioni personali o familiari esulano dal perimetro.

Se una condizione non è soddisfatta, segnala: *"Questa decisione non sembra avere un trade-off deliberabile [o: non rientra nel perimetro di Deliberato]. Vuoi comunque procedere con il council?"* e attendi la risposta dell'utente prima di continuare.

### Step 3 — Convocazione advisor (5 in parallelo)

Spawna 5 sub-agenti in parallelo, uno per advisor, ognuno con il proprio prompt template (definito nel file della modalità attiva). Ogni advisor produce una risposta di 200-300 parole, in italiano, senza preamboli. Il parallelo è obbligatorio: previene il bias di posizione (chi risponde per primo influenza gli altri).

Usa i prompt template completi definiti nel file della modalità attiva (sezione "I 5 advisor", sotto-sezione "Prompt template" per ciascun advisor). Ogni template include lo stile di pensiero specifico e i guardrail obbligatori dell'advisor — non usare prompt generici che li ometterebbero.

Struttura di riferimento dei prompt (ogni modalità la implementa con contenuto specifico):

```
Sei {nome_advisor} in un council deliberativo.

Il tuo stile di pensiero: {descrizione_stile}

[brief inquadrato]

Rispondi dalla tua prospettiva. Sii diretto e specifico. Non cercare 
equilibrio, non hedge. Vai a fondo nel tuo angolo di analisi: gli altri 
advisor copriranno gli angoli che tu non copri.

[guardrail specifici dell'advisor, definiti nel file modalità]

Lunghezza: 200-300 parole. Nessun preambolo, vai dritto all'analisi.
```

**Presentazione in chat degli advisor:** ogni risposta viene mostrata come accordion `<details>/<summary>`. Il `<summary>` riporta il nome dell'advisor e la sua idea chiave in max 80 parole. La risposta completa è visibile espandendo l'accordion ed è usata integralmente nella peer review — non viene abbreviata internamente.

```html
<details>
<summary><strong>[Nome Advisor]</strong> — [punto principale in 1-2 frasi, max 80 parole]</summary>

[risposta completa 200-300 parole]

</details>
```

### Step 4 — Peer review anonima

Raccogli le 5 risposte degli advisor. Anonimizzale come Risposta A, B, C, D, E, **randomizzando l'ordine** (così non c'è bias posizionale). Spawna 5 nuovi sub-agenti reviewer in parallelo (uno per advisor): ogni reviewer vede tutte e 5 le risposte anonimizzate e risponde a 3 domande.

Prompt template reviewer:

```
Stai revisionando il lavoro di un council deliberativo. Cinque advisor 
hanno risposto indipendentemente a questa domanda:

---
{brief_inquadrato}
---

Ecco le risposte anonimizzate:

**Risposta A:** {risposta_a}
**Risposta B:** {risposta_b}
**Risposta C:** {risposta_c}
**Risposta D:** {risposta_d}
**Risposta E:** {risposta_e}

Rispondi a queste tre domande. Sii specifico. Cita le risposte per lettera.

1. Quale risposta è la più forte? Perché?
2. Quale risposta ha il blind spot più grande? Cosa manca?
3. Cosa hanno mancato TUTTE e cinque le risposte e che il council dovrebbe 
   considerare?

Lunghezza max 200 parole. Sii diretto.
```

### Step 5 — Chairman synthesis

Un singolo agente chairman riceve: il brief, le 5 risposte de-anonimizzate (chi ha detto cosa), le 5 peer review. Produce il verdetto finale nella struttura fissa.

Prima di costruire il prompt, controlla se il file della modalità attiva contiene una sezione `## Istruzioni per il chairman`. Se presente, appendi quelle istruzioni al prompt del chairman, dopo la struttura del verdetto e prima dell'istruzione finale "Sii diretto."

I nomi degli advisor (`{advisor_N_nome}`) sono quelli definiti nel file della modalità attiva — vanno letti e iniettati nel prompt prima di inviarlo al chairman.

Prompt template chairman:

```
Sei il Chairman di un council deliberativo. Devi sintetizzare il lavoro 
di 5 advisor e delle relative peer review in un verdetto finale.

La decisione portata al council:

---
{brief_inquadrato}
---

RISPOSTE DEGLI ADVISOR:

**{advisor_1_nome}:** {risposta_1}
**{advisor_2_nome}:** {risposta_2}
**{advisor_3_nome}:** {risposta_3}
**{advisor_4_nome}:** {risposta_4}
**{advisor_5_nome}:** {risposta_5}

PEER REVIEW:
{tutte_le_5_review}

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
l'argomento del dissenter è più forte, puoi schierarti col dissenter — 
spiegando perché. Il punto del council è dare chiarezza, non equilibrio 
politicamente corretto.
```

### Step 6 — Presentazione in chat

Il verdetto viene presentato direttamente in chat in markdown, senza generare file. Eccezione: se l'utente chiede esplicitamente di salvare il transcript, salva un file `transcript-deliberato-{YYYYMMDD-HHmm}.md` nella cartella corrente (o `./active/` se esiste).

## Fast Council

Flusso abbreviato per decisioni importanti che non richiedono il processo completo. Attivato dai trigger Fast Council definiti nel frontmatter.

### FC-Step 1 — Identificazione modalità

Identica al Full Council: stessa logica di routing verso le 6 modalità. Stessa comunicazione: *"Avvio Deliberato Fast Council in modalità [nome modalità]."*

### FC-Step 2 — Intake rapido (2 domande)

Poni solo due domande, in un unico messaggio:

1. **La decisione** — Qual è la scelta concreta? Descrivi le opzioni o il go/no-go.
2. **Cosa è in gioco** — Cosa succede se sbagli? Cosa succede se aspetti? C'è una deadline reale?

Se l'utente ha già fornito entrambe le informazioni nel messaggio iniziale, salta l'intake e segnala: *"Ho abbastanza contesto per procedere."*

Prima di avviare il council, verifica che la decisione soddisfi entrambe le condizioni:
1. **Trade-off genuino** — esistono almeno due opzioni con vantaggi e costi reali; non c'è una risposta già quasi scontata.
2. **Perimetro professionale** — la decisione rientra in una delle 6 modalità (business, strategia aziendale, professionale). Decisioni personali o familiari esulano dal perimetro.

Se una condizione non è soddisfatta, segnala: *"Questa decisione non sembra avere un trade-off deliberabile [o: non rientra nel perimetro di Deliberato]. Vuoi comunque procedere con il council?"* e attendi risposta.

### FC-Step 3 — Convocazione 3 advisor (in parallelo)

Spawna 3 sub-agenti in parallelo usando i **primi 3 advisor** definiti nel file della modalità attiva (Advisor 1, 2, 3). Stessi prompt template completi del Full Council — inclusi guardrail specifici. Lunghezza invariata: 200-300 parole ciascuno.

I primi 3 advisor per modalità:

| Modalità | Advisor 1 | Advisor 2 | Advisor 3 |
|---|---|---|---|
| Marketing & AI Strategy | Lo Stratega di Prodotto | L'Economista Pragmatico | Il Realista Operativo |
| Pricing | Lo Stratega del Valore | L'Analista di Unit Economics | Il Comportamentalista |
| Hiring e Team | Lo Stratega del Team | Il Numerico | Il Costruttore di Cultura |
| Direzione Strategica | L'Analista dei Segnali | Il Guardiano del Focus | Il Costruttore di Moat |
| Partnership e Distribuzione | Lo Stratega del Canale | Il Negoziatore | Il Realista delle Dipendenze |
| Capitali e Finanza | Il Custode della Missione | Il Matematico del Capitale | Il Conoscitore di Investitori |

**Presentazione in chat degli advisor:** stessa struttura accordion del Full Council — `<details>/<summary>` con idea chiave in max 80 parole nel summary, risposta completa dentro.

### FC-Step 4 — Chairman synthesis diretta

Il chairman riceve il brief e le 3 risposte de-anonimizzate. Nessuna peer review. Produce un verdetto compatto.

Prima di costruire il prompt, controlla se il file della modalità attiva contiene una sezione `## Istruzioni per il chairman`. Se presente, applica anche qui.

Prompt template chairman Fast Council:

```
Sei il Chairman di un council deliberativo. Tre advisor hanno analizzato 
questa decisione da angoli diversi. Sintetizza in un verdetto diretto.

La decisione portata al council:

---
{brief_inquadrato}
---

RISPOSTE DEGLI ADVISOR:

**{advisor_1_nome}:** {risposta_1}
**{advisor_2_nome}:** {risposta_2}
**{advisor_3_nome}:** {risposta_3}

Produci il verdetto usando ESATTAMENTE questa struttura:

## Verdetto Fast Council: {topic_breve}

### Dove il council converge
{1_2_punti_di_accordo_tra_advisor}

### Il disaccordo principale
{se_esiste_un_disaccordo_genuino_presentalo_con_entrambi_i_lati — 
se_non_esiste_scrivi_"Nessun disaccordo rilevante."}

### La raccomandazione
{raccomandazione_chiara_senza_hedge}

### Confidence
ALTA / MEDIA / BASSA — {motivazione_1_frase}

### Prossime 24 ore
{una_cosa_concreta_da_fare_subito}

---
*Questo verdetto non sostituisce consulenza legale, finanziaria o fiscale 
specialistica. Verificare aspetti compliance (GDPR/AI Act) con specialista 
quando rilevante.*

Sii diretto. Se un advisor ha l'argomento più forte, schierati con lui — 
anche se è in minoranza. Niente equilibrio diplomatico.
```

Il verdetto viene presentato direttamente in chat in markdown. Alla fine, offri l'opzione: *"Vuoi il Full Council su questa decisione per un'analisi più approfondita con peer review?"*

## Note importanti

- **Full Council**: sempre 5 advisor in parallelo, mai sequenziali. La parallelizzazione previene il bias di chi parla per primo.
- **Fast Council**: 3 advisor in parallelo, nessuna peer review, chairman diretto. Offri sempre il passaggio al Full Council alla fine del verdetto fast.
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
intake e protocolli ridisegnati per founder, manager e professionisti italiani e per il contesto UE.
