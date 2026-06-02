# Esempio di sessione: build vs buy per screening CV con AI

## Il contesto

Una PMI di consulenza HR con 15 persone e 1.2M€ di fatturato annuo sta valutando di introdurre AI nei propri processi di screening candidati. L'azienda lavora in B2B con PMI italiane e si trova in una fase di crescita in cui la differenziazione rispetto ai competitor è diventata una pressione concreta. Un competitor ha già annunciato di aver integrato AI nel proprio servizio. Il founder vuole capire se costruire un agente custom su API Claude/OpenAI o acquistare un SaaS verticale esistente — e se farlo adesso o aspettare.

Il caso è stato portato al council tramite la frase: *"Convoca il council: devo decidere se costruire un agente AI per lo screening CV o comprare una soluzione SaaS."*

## L'intake

**Q: Qual è la scelta concreta che stai affrontando? Descrivi le opzioni.**

R: Build vs buy. Opzione A: costruire internamente un agente AI per lo screening CV, integrato nel nostro CRM, usando le API di Claude o OpenAI. Un developer freelance mi ha quotato 6.000€ per un prototipo. Opzione B: acquistare un SaaS verticale — ho guardato Teamtailor, Recruitee, Workable. Tutti hanno una qualche forma di AI integrata, ma nessuno fa esattamente quello che voglio.

**Q: Che azienda è? In che fase si trova?**

R: Consulenza HR, 15 persone, fatturato 1.2M€, B2B in Italia. Clienti: PMI manifatturiere e di servizi, tra 20 e 200 dipendenti. Siamo in fase di crescita — negli ultimi 18 mesi abbiamo aumentato fatturato del 30%. Il nostro competitor principale ha comunicato di aver integrato AI nel suo servizio di screening. Non sappiamo esattamente cosa ha fatto, ma ci sta mettendo pressione.

**Q: Quali sono i vincoli?**

R: Budget massimo 8.000€ per il setup iniziale, poi sono disposto a sostenere costi ricorrenti ragionevoli. Ho un freelance disponibile 1 giorno/settimana per circa 3 mesi. Zero competenze AI in-house — nessuno nel team sa sviluppare. Deadline: voglio qualcosa in produzione prima della fine del Q3, altrimenti perdo l'effetto di poterlo comunicare ai clienti nel ciclo di rinnovi autunnali.

**Q: Cosa hai già considerato? Perché non hai ancora deciso?**

R: Ho guardato i SaaS — funzionano, ma nessuno si integra bene col nostro CRM attuale e tutti fanno matching "generico". Ho parlato con il developer che mi ha quotato 6K per un prototipo, ma non so se quel prototipo è manutenibile nel tempo o se diventa un problema quando lui non è disponibile. L'ho rimandato per 3 mesi perché non riuscivo a capire se stavo sottovalutando il rischio tecnico.

**Q: Cosa succede se sbagli? E se aspetti?**

R: Se costruisco e non funziona, ho speso 8K€ e 3 mesi per niente, e devo ricominciare. Se compro un SaaS che non fa quello che mi serve, mi ritrovo a pagare per qualcosa che non uso davvero o che non posso mostrare ai clienti come differenziatore. Se aspetto 6 mesi, rischio di presentarmi ai rinnovi autunnali senza nulla di concreto — e il competitor nel frattempo continua a muoversi.

## Le risposte degli advisor

### Come le vede il reviewer: risposte anonimizzate (A/B/C/D/E)

Per la peer review, le risposte vengono presentate in ordine randomizzato e anonimizzato. Il mapping tra lettere e advisor viene rivelato solo nella fase di sintesi del chairman (sezione successiva).

---

**Risposta A:**

Lo screening automatico dei CV rientra quasi certamente nella categoria dei sistemi ad alto rischio secondo l'AI Act (Allegato III, punto 4: sistemi di IA utilizzati per assunzione o selezione del personale). Questo non è un dettaglio tecnico, è un vincolo legale operativo. Se il sistema viene usato per prendere o influenzare decisioni su candidati reali — anche solo per filtrare chi viene contattato — scattano obblighi precisi: valutazione della conformità, supervisione umana significativa e verificabile, documentazione del sistema, registro dell'utilizzo.

Il SaaS acquistato da un vendor europeo consolidato potrebbe essere già conforme — ma "potrebbe" non basta. Va verificato con documentazione esplicita prima di qualsiasi firma. Un sistema custom costruito da un freelance in 3 mesi, quasi certamente, non sarà conforme. Non perché il freelance sia incompetente, ma perché la conformità AI Act su sistemi HR richiede un processo di valutazione che nessun prototipo da 6K€ può ragionevolmente includere.

Sul GDPR: i dati dei CV sono dati personali e spesso rivelano informazioni sensibili (salute, origine, religione, sindacati). Il trattamento automatizzato di queste informazioni richiede una base legale esplicita, una privacy impact assessment per i trattamenti ad alto rischio, e in alcuni casi il consenso esplicito del candidato. Nessuna delle due opzioni è neutra su questo piano.

Sul lock-in: sia il custom che il SaaS creano dipendenza. Il SaaS crea dipendenza dal vendor — se cambia prezzi, policy o smette di supportare l'integrazione col CRM, sei bloccato. Il custom crea dipendenza dal freelance che ha scritto il codice. Se lui non è disponibile a sei mesi, hai un sistema che nessuno sa mantenere. Entrambe le dipendenze sono reali. Quella col freelance è più fragile.

---

**Risposta B:**

Facciamo i numeri concreti. Budget disponibile: 8.000€. Il freelance è quotato 6.000€ per il prototipo. Rimangono 2.000€ di buffer. Il freelance lavora 1 giorno/settimana per 3 mesi: circa 12-13 giorni di lavoro effettivo. È un prototipo, non un sistema robusto.

Costi ricorrenti del custom: API Claude o OpenAI per un uso business-scale (diciamo 500-1.000 CV/mese) si aggirano intorno ai 50-200€/mese a seconda del modello e del volume. Aggiungi manutenzione del codice: se il freelance fa 4 ore/mese a 80€/ora, sono 320€/mese solo per tenerlo in piedi. Totale costo ricorrente stimato: 400-520€/mese.

SaaS verticale (Recruitee, Workable, livello base-intermedio per una PMI di questa dimensione): 200-400€/mese, tutto incluso, con supporto e aggiornamenti.

Il costo mensile del custom è più alto, non più basso. E questo assume che il prototipo funzioni senza problemi.

Payback del custom rispetto al SaaS: se il custom costa 500€/mese e il SaaS 300€/mese, hai 200€/mese di delta negativo oltre all'investimento iniziale di 8K€. Non c'è payback operativo, solo un ipotetico valore di differenziazione. Quel valore esiste? Dipende da quanto il custom fa cose che il SaaS non può fare. Se la risposta è "screening più preciso che porta a vincere gare", va quantificato: una gara in più a trimestre da 15K€ vale 60K€/anno — lì il calcolo cambia radicalmente. Ma prima di investire, quella tesi va validata, non assunta.

---

**Risposta C:**

Il punto non è build vs buy in astratto. È: cosa stai cercando di comunicare al mercato?

Se il differenziatore che vuoi costruire è "noi usiamo AI nei nostri processi HR meglio dei competitor", allora hai bisogno di una storia credibile da raccontare ai tuoi clienti PMI. Un SaaS white-label non te la dà — stai usando gli stessi tool dei tuoi competitor, potenzialmente. Un agente custom costruito su misura ti dà la narrativa dell'innovazione interna, ma solo se funziona in modo affidabile. Un prototipo fragile che si rompe davanti a un cliente ti toglie la storia, non te la dà.

La domanda strategica vera è diversa però: stai vendendo AI come componente del tuo servizio ai clienti, oppure stai usando AI per migliorare la tua delivery interna e abbassare i costi operativi? Queste sono due posizioni completamente diverse.

Se è la prima — il differenziatore di mercato conta, e il custom ha senso nel lungo periodo. Se è la seconda — e per una PMI di consulenza di 15 persone è probabilmente la risposta più onesta — allora quello che importa è l'efficienza operativa: quante ore risparmi sullo screening, quanto migliora la qualità dei candidati che presenti ai clienti. In quel caso il SaaS che funziona e si aggiorna automaticamente batte il custom fragile. Metti le energie nell'uso intelligente dello strumento, non nella sua costruzione.

Il competitor che accelera non cambia necessariamente questa logica: non sai cosa ha costruito, non sai se sta vendendo il tool o solo migliorando la delivery interna. Prima di reagire alla pressione del competitor, vale la pena capire cosa ha fatto davvero.

---

**Risposta D:**

1 freelance. 1 giorno/settimana. 3 mesi. Questo è il tuo team di sviluppo AI.

Lunedì mattina, chi sistema il problema quando l'agente smette di funzionare? Il freelance — se è disponibile, se non ha altri clienti urgenti, se non è in ferie. Chi aggiorna le chiamate API quando OpenAI depreca un modello o cambia gli endpoint? Succede ogni 6-12 mesi. Chi monitora i log per capire se lo screening sta funzionando o sta facendo scelte sbagliate? Chi gestisce il caso in cui un candidato si lamenta di una valutazione automatica — con la PMI esposta a contestazioni?

Il prototipo da 6K€ è una cosa. Mettere in produzione un sistema AI che tratta dati sensibili di candidati reali, con accesso al CRM aziendale, in un contesto B2B dove i clienti ti affidano i loro processi HR — è un'altra. Non per complessità tecnica astratta, ma per le conseguenze concrete di ogni singolo problema: un agente che sbaglia un filtro porta a non contattare un candidato qualificato. Un agente che si rompe durante una selezione urgente per un cliente blocca il tuo processo in un momento critico.

Il SaaS ha un team di supporto, ha uptime SLA, ha un ciclo di aggiornamenti che non dipende dal tuo freelance. Ha anche dei limiti — non fa esattamente quello che vuoi. Ma "non fa esattamente quello che voglio" è un problema molto più gestibile di "si rompe e nessuno sa ripararlo".

---

**Risposta E:**

Prima di scegliere tra costruire e comprare, una domanda più scomoda: sei sicuro che lo screening dei CV sia il posto giusto dove mettere l'AI?

La decisione è arrivata al council come "build vs buy", ma quel framing nasconde un'assunzione mai messa in discussione — che l'AI nello screening sia il differenziatore da inseguire. È vero, o è solo dove è andato il competitor? Lo screening automatico è ormai una commodity: ogni SaaS HR lo fa, e lo farà meglio e più a buon mercato di qualsiasi cosa tu possa costruire in 3 mesi con un freelance. Mettere l'AI dove la mettono tutti non costruisce un vantaggio — ti allinea, non ti differenzia.

Dove sta il tuo asset reale? In 18 mesi di crescita hai accumulato qualcosa che i SaaS generici non hanno: lo storico di chi hai piazzato, in quali aziende, con quali esiti nel tempo. Quello è il dato proprietario. Un'AI che predice il fit tra candidato e azienda sulla base dei tuoi placement passati è un moat difendibile. Un'AI che filtra CV come tutti gli altri non lo è.

E la pressione del competitor? Reagire a "il competitor ha messo l'AI nello screening" mettendo l'AI nello screening significa seguirlo, non superarlo. Quando il tuo sistema sarà pronto, lui sarà già altrove.

Riformulazione: la domanda non è build vs buy. È "qual è l'unico punto in cui l'AI, applicata ai miei dati, costruisce qualcosa che nessun SaaS può copiare" — e lo screening generico probabilmente non è quello.

### Le risposte de-anonimizzate

Nella sintesi del chairman, le risposte vengono reattribuite ai rispettivi advisor. Il mapping è il seguente: A = Il Contrarian AI-aware, B = L'Economista Pragmatico, C = Lo Stratega di Prodotto, D = Il Realista Operativo, E = L'Espansore.

## Le peer review

Le 5 peer review vengono prodotte in parallelo. Ogni advisor-reviewer vede le 5 risposte anonimizzate (A/B/C/D/E) e risponde alle 3 domande standard.

---

**Review 1 — Lo Stratega di Prodotto recensisce:**

La risposta più forte è D. Porta il problema a terra in modo brutale e non ci sono contromisure retoriche possibili: "chi debugga il freelance quando è in ferie" è una domanda a cui non si può rispondere con ottimismo. Scala immediatamente da astratto a concreto.

La risposta con il blind spot più grande è C — la mia. Riduce tutto a una dicotomia netta (AI come servizio ai clienti vs AI per l'efficienza interna) che semplifica troppo. Una PMI di consulenza HR in crescita può stare in entrambi i quadranti contemporaneamente, e la scelta tra build e buy non è necessariamente diversa nei due casi.

Cosa hanno mancato tutte e cinque: nessuno ha l'informazione concreta su cosa stia facendo il competitor. E si è avvicinato di più — ha messo in discussione l'idea stessa di inseguirlo — ma resta il fatto che il founder dice solo che il competitor "ha integrato AI nel suo servizio", senza sapere se ha costruito qualcosa di custom o ha acquistato un SaaS. Saperlo cambia completamente la valutazione del differenziatore strategico. Se il competitor ha comprato Workable, costruire un custom potrebbe essere la mossa giusta. Se ha un team tecnico interno e qualcosa di proprietario, il confronto cambia.

---

**Review 2 — L'Economista Pragmatico recensisce:**

La risposta più forte è A. Non per il calcolo economico — B ha fatto meglio su quello — ma perché ha identificato il rischio con le conseguenze economiche più gravi: la non-conformità AI Act non è un rischio gestibile con un buffer di 2K€. È un rischio di blocco del sistema, di sanzione, di danno reputazionale in un mercato B2B dove la fiducia è tutto. Il costo di un incidente compliance può azzerare anni di margine.

La risposta con il blind spot più grande è B — la mia. Ho calcolato il payback sull'efficienza operativa, ma ho lasciato il valore del differenziatore come variabile indipendente da verificare senza suggerire come verificarla. C ed E hanno fatto meglio su questo: C ha posto la domanda giusta (cosa stai vendendo?), E ha rimesso in discussione l'intero campo di battaglia (lo screening è davvero dove l'AI conta?). Il mio calcolo è tecnicamente corretto ma costruito su un frame che entrambi mettono in dubbio.

Cosa hanno mancato tutte e cinque: nessuno ha messo numeri sul costo di switching a 6 mesi. Se il founder inizia col SaaS e poi vuole costruire il custom, quanto costa passare dall'uno all'altro? E viceversa: se costruisce il custom e poi si rende conto che non funziona, quanto costa abbandonarlo e passare al SaaS con dati già inseriti, processi già avviati, clienti già abituati al flusso? E ha riaperto bene la domanda strategica, ma nemmeno lui l'ha quantificata.

---

**Review 3 — Il Realista Operativo recensisce:**

La più forte è A perché introduce un vincolo esterno che non dipende dalla bravura del team, dalla qualità del freelance o dalle intenzioni del founder. Una legge è una legge. D è forte ma si ferma a un livello che chiunque abbia esperienza operativa conosce già — il single point of failure del freelance è evidente. A porta qualcosa che in molti non hanno ancora considerato concretamente.

Il blind spot più grande è in C: il posizionamento esterno è importante, ma è un lusso che si affronta dopo aver risolto i problemi operativi e compliance. Ragionare sul differenziatore di mercato prima di aver verificato che il sistema possa girare in produzione in modo legale è costruire sopra fondamenta instabili.

Cosa hanno mancato tutte e cinque: nessuno ha suggerito la terza via ovvia. E ha riformulato bene il "dove" mettere l'AI, ma non il "quando" — e qui sta il punto. Non è obbligatorio scegliere tra build adesso e buy per sempre. La sequenza logica sarebbe: SaaS per 6-12 mesi per capire i requisiti reali e il comportamento degli utenti, poi costruire il custom su un brief preciso — con un team tecnico già ingaggiato e una knowledge base del proprio uso reale. Questo riduce drasticamente il rischio di costruire la cosa sbagliata.

---

**Review 4 — Il Contrarian AI-aware recensisce:**

La più forte è D perché tocca il rischio che gli altri tendono a minimizzare come "problema tecnico": la dipendenza da una singola persona non è un rischio tecnico, è un rischio di business. Un sistema critico che dipende dalla disponibilità di un singolo freelance part-time è fragile per definizione, indipendentemente dalla qualità del codice.

Il blind spot più grande è in B: il calcolo del payback assume che il tool funzioni come previsto e continui a farlo nel tempo. Non include i costi di refactoring quando le API cambiano (e cambiano: OpenAI ha già deprecato modelli usati in produzione da molte PMI), i costi di non-compliance se emerge un problema legale, i costi di un incidente di sicurezza su dati CV. Il calcolo è corretto nelle sue premesse, ma le premesse sono ottimistiche.

Cosa hanno mancato tutte e cinque: nessuno ha considerato i vincoli contrattuali dei clienti B2B della PMI. In ambito HR B2B, il cliente finale — la PMI che affida il processo di selezione — potrebbe avere policy interne sull'uso di AI nei processi di valutazione del personale. Alcune aziende lo vietano esplicitamente nei contratti con fornitori. Prima di investire in qualsiasi soluzione, una telefonata ai 3 clienti principali per capire se hanno vincoli su questo è un'ora di lavoro che può cambiare tutto il quadro.

---

**Review 5 — L'Espansore recensisce:**

La più forte è C. È l'unica, oltre alla mia, che non dà per scontato l'obiettivo: invece di ottimizzare il "come" (build o buy), chiede "cosa stai davvero vendendo". Tutto il resto del council ha fatto un ottimo lavoro su una domanda che potrebbe essere quella sbagliata.

Il blind spot più grande è in B. Il calcolo del payback è preciso e onesto, ma è preciso su un investimento che forse non andrebbe fatto in quel punto. Mettere numeri al millimetro sullo screening quando lo screening è una commodity significa misurare con cura la cosa sbagliata. A e D sono rigorosi sui rischi — compliance e operatività — ma anche loro accettano implicitamente che lo screening sia il campo da gioco.

Cosa hanno mancato tutte e cinque, me compreso: nessuno ha validato la domanda. Diamo per scontato che i clienti vogliano AI nello screening perché il competitor l'ha fatto. Ma nessuno ha proposto di verificarlo prima di spendere — né build né buy. Una conversazione con 3-4 clienti su "vi interessa, e paghereste di più per questo?" vale più di qualsiasi prototipo. Si rischia di costruire o comprare la risposta a una domanda che il mercato non ha fatto.

## Il verdetto del council

## Verdetto del Council: build vs buy per screening CV con AI

### Dove il council è d'accordo

Il freelance part-time come unica risorsa tecnica è il rischio operativo principale, indipendentemente dalla scelta. Su questo gli advisor convergono: il build richiede competenze tecniche continuative che non esistono nel team. Il SaaS le esternalizza al vendor. Non è una questione di competenza del freelance, è una questione di struttura: un sistema AI in produzione su dati sensibili non può dipendere da 1 giorno/settimana di disponibilità esterna.

Il rischio compliance (GDPR + AI Act) non è negoziabile. Lo screening automatico di CV rientra quasi certamente nella categoria high-risk dell'AI Act (Allegato III, sistemi di selezione del personale). Qualsiasi soluzione — build o buy — deve dimostrare conformità prima di andare in produzione con dati reali di candidati. Questo non è un rischio da gestire dopo il lancio, è un prerequisito.

### Dove il council è in disaccordo

Lo Stratega e il Realista convergono sul fatto che il differenziatore esterno è secondario rispetto all'operatività. L'Economista non ha preso posizione esplicita, ma il suo calcolo lascia aperta la possibilità che il valore stia nelle gare vinte — avvicinandosi alla posizione del founder che sente la pressione del competitor. Disaccordo genuino: la pressione competitiva esterna cambia il calcolo?

La risposta onesta è: non lo sappiamo, perché nessuno sa cosa ha costruito il competitor. Se ha integrato un SaaS, il custom potrebbe dare un vantaggio reale. Se ha un team tecnico interno e sta costruendo qualcosa di proprietario, la competizione è su un piano diverso. Questa variabile mancante è una di quelle che potrebbero ribaltare la raccomandazione.

C'è un disaccordo più profondo, sollevato da L'Espansore: tre advisor su cinque danno per scontato che lo screening sia il campo di battaglia giusto per l'AI. L'Espansore lo nega — lo screening è una commodity che ogni SaaS fa meglio, mentre il vero asset difendibile è il dato proprietario sui placement passati. Non è un dettaglio: se ha ragione, l'intera decisione build-vs-buy sullo screening è secondaria rispetto a dove l'AI dovrebbe davvero andare. Lo Stratega si avvicina a questa posizione ("cosa stai vendendo?"), gli altri la mancano.

### Blind spot emersi nella revisione

Tre blind spot significativi non coperti dai singoli advisor nelle loro analisi iniziali.

Primo: la terza via non è stata considerata. Non è obbligatorio scegliere tra build adesso e buy per sempre. La sequenza logica — SaaS per 6-12 mesi per capire i requisiti reali, poi costruire il custom con un brief preciso — riduce il rischio di costruire la cosa sbagliata e conserva il budget per un momento in cui sarà speso meglio.

Secondo: i vincoli contrattuali dei clienti B2B non sono stati considerati. In ambito HR B2B, il cliente finale che affida i propri processi di selezione potrebbe avere policy interne sull'uso di AI nelle valutazioni del personale. Alcune aziende lo vietano esplicitamente. Prima di qualsiasi investimento, una telefonata ai 3 clienti principali è un'ora di lavoro che può cambiare tutto il quadro — e non richiede né budget né decisioni tecniche.

Terzo, emerso dalla revisione de L'Espansore: la domanda non è stata validata. Tutto il council — me compreso — assume che i clienti vogliano AI nello screening perché lo vuole il founder, spinto dal competitor. Ma nessuno ha verificato che ci sia domanda reale. La stessa telefonata ai clienti che serve per i vincoli contrattuali può sondare l'interesse: "vi interessa l'AI nello screening, e avrebbe valore per voi?" Costruire o comprare la risposta a una domanda che il mercato non ha posto è lo spreco più costoso di tutti.

### La raccomandazione

Non costruire adesso. Adottare un SaaS verticale per i prossimi 6-12 mesi, con tre condizioni non negoziabili.

Primo: scegliere un SaaS con documentazione esplicita sulla conformità AI Act e GDPR. Non assumerla, verificarla prima della firma. Chiedere al vendor: il vostro sistema rientra nella categoria high-risk AI Act? Avete completato la valutazione di conformità? Dove è documentata? Un vendor che non sa rispondere va scartato.

Secondo: usare i 6 mesi di SaaS per documentare cosa funziona, cosa manca e come i clienti reagiscono all'AI nello screening. Quel documento — scritto in modo rigoroso — diventa il brief per un eventuale build futuro, quando i requisiti saranno chiari e non immaginati.

Terzo: prima di qualsiasi altra azione, fare una telefonata ai 3 clienti principali con un duplice scopo — capire se hanno policy interne sull'uso di AI in HR (vincolo) e se l'AI nello screening avrebbe per loro un valore reale (domanda). Questa azione richiede 2 ore, non 3 mesi, e può cambiare completamente il perimetro di quello che è fattibile e sensato. Se emerge che il valore difendibile non è nello screening ma nel matching basato sui placement storici — come ha sostenuto L'Espansore — il budget va ripensato su quell'obiettivo, non sullo screening.

Il budget di 8.000€ non viene speso adesso. Viene conservato per un build futuro, con requisiti reali e un team tecnico già identificato.

### Confidence

MEDIA — La raccomandazione è robusta sui rischi operativi e compliance, che sono verificabili e concreti. La variabile che la renderebbe sbagliata è se il competitor sta costruendo qualcosa di realmente differenziante che porta a perdere gare nel breve termine — informazione che non è disponibile e che vale la pena raccogliere prima di qualsiasi decisione.

### Piano d'azione

- **Prossime 24 ore:** Preparare 3 domande dirette per i clienti principali (hanno policy interne sull'AI in HR? Hanno vincoli contrattuali? L'AI nello screening avrebbe per voi un valore reale, e per cosa pagherreste?) e calendarizzare le chiamate entro la settimana. Costo: zero.
- **Prossimi 7 giorni:** Richiedere documentazione compliance AI Act e GDPR ai 2-3 SaaS in shortlist. Scartare quelli che non la forniscono o la vagheggiano. Parallelamente, fare una ricerca informale su cosa ha effettivamente implementato il competitor — LinkedIn, press release, eventuali demo pubbliche.
- **Prossimi 30 giorni:** Sulla base delle risposte dei clienti e della verifica compliance dei vendor, selezionare e attivare il SaaS. Aprire un documento interno "Requisiti screening AI" da aggiornare ogni mese — sarà il brief per il build futuro.

---
*Questo verdetto non sostituisce consulenza legale, finanziaria o fiscale specialistica. La classificazione AI Act di sistemi di screening del personale richiede verifica con uno specialista di compliance prima della messa in produzione con dati reali di candidati.*
