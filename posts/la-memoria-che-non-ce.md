---
title: La memoria che non c'è
description: Ogni conversazione riparte da zero, eppure il modello sembra ricordare. Cos'è davvero il contesto, perché a metà di un lavoro lungo "dimentica", e come organizzarsi di conseguenza.
date: 2026-06-16
author: vincenzo
tags: [contesto, memoria, fondamenta, LLM]
image: /images/posts/cover-la-memoria-che-non-ce.png
lang: it
---

![La memoria che non c'è](/images/posts/cover-la-memoria-che-non-ce.png)

Perché un modello che sembra ricordare non ricorda niente, e cosa vi rileggono davvero a ogni messaggio. Cosa succede alle istruzioni che finiscono nel mezzo di una conversazione lunga, le quattro abitudini che ne discendono, e il motivo per cui l'assenza di memoria — a saperla usare — è una risorsa e non un difetto.

C'è un momento, in quasi tutte le conversazioni lunghe con un modello, in cui qualcosa si incrina. Avevate stabilito all'inizio che il testo era per un cliente tedesco, che il tono doveva restare formale, che i prezzi andavano in euro. Quaranta messaggi dopo, il modello scrive "caro amico" e mette i dollari. Non è impazzito. È successa una cosa precisa, e capirla cambia il modo di lavorare.

## Il modello non ricorda niente

Partiamo dal fatto che sorprende di più: un modello linguistico non ha memoria. Nessuna. Fra una risposta e la successiva non conserva nulla, e a ogni messaggio che mandate riceve **l'intera conversazione da capo** — tutto quello che avete scritto voi, tutto quello che ha risposto lui — e la rilegge per intero prima di produrre la frase successiva.

Quella che sembra memoria è questo: un testo sempre più lungo che qualcuno gli rimette davanti ogni volta. Il modello non "si ricorda" del cliente tedesco; lo *rilegge*, se è ancora lì da leggere.

Vale anche fra una conversazione e l'altra. Chiudete la chat, ne aprite una nuova, e il modello non sa chi siete. I servizi che sembrano ricordarsi di voi — "l'utente preferisce risposte brevi", "sta lavorando a un progetto in Svelte" — hanno costruito un meccanismo esterno: appunti presi durante le conversazioni precedenti e reinseriti di nascosto in cima alla nuova. Utile, ma è un taccuino, non una memoria. E come tutti i taccuini contiene quello che qualcuno ha deciso di annotare, non quello che è successo.

## La finestra, e cosa succede ai bordi

Lo spazio in cui il modello legge ha un limite, che si chiama finestra di contesto. Si misura in token — frammenti di parola — e nei modelli attuali è grande: centinaia di pagine. Sembra abbastanza per non pensarci mai. Non lo è, per due motivi.

Il primo è che si riempie più in fretta di quanto sembri. Una conversazione di lavoro vera non è fatta solo delle vostre frasi: ci sono i documenti incollati, le versioni successive dello stesso testo, le risposte lunghe del modello. Un pomeriggio su un contratto può macinare l'equivalente di un romanzo.

Il secondo è più sottile, e lo si scopre solo lavorando: **il modello non legge tutta la finestra con la stessa attenzione**. Le cose scritte all'inizio e quelle scritte alla fine pesano di più; quelle nel mezzo tendono a sbiadire. Il fenomeno è noto e misurato — in letteratura lo chiamano *lost in the middle* — e spiega esattamente l'incidente del cliente tedesco: quell'istruzione non era sparita, era al minuto dodici di una conversazione di due ore, sepolta dove l'attenzione è più bassa.

Con una persona succederebbe lo stesso, peraltro. Se dettate a un collaboratore per due ore, la raccomandazione fatta di sfuggita all'inizio si perde. La differenza è che il collaboratore vi direbbe "scusa, com'era la storia dei prezzi?" — il modello no. Tira dritto, con la stessa sicurezza di sempre.

## Le conseguenze pratiche

Da questo quadro discendono quattro abitudini che valgono più di qualsiasi trucco di formulazione.

**Le istruzioni importanti si ripetono.** Non per sfiducia: per fisica del sistema. Quando un lavoro è lungo, le tre regole che contano — tono, destinatario, vincoli — conviene riscriverle al momento in cui servono, invece di confidare che l'istruzione data un'ora fa sia ancora "in vista". Una riga: "ricorda: tono formale, prezzi in euro". Costa cinque secondi e salva revisioni intere.

**Le conversazioni lunghe si chiudono.** Quando una chat ha accumulato tre versioni scartate di un testo, due digressioni e un documento incollato per sbaglio, quel materiale non è neutro: il modello continua a leggerlo tutto, e le versioni scartate inquinano quella buona. Il gesto giusto è controintuitivo: chiudere, aprire una conversazione nuova, e portarsi dietro solo un riassunto di quello che serve. Due minuti di trasloco, e il modello torna lucido.

**Il riassunto di trasloco lo scrive lui.** Prima di chiudere: "riassumi in dieci righe cosa abbiamo deciso e cosa resta da fare, in modo che io possa incollarlo in una nuova conversazione". È una delle richieste più utili che esistano, e non la fa quasi nessuno.

**I documenti importanti stanno in cima o in fondo.** Se dovete far leggere quaranta pagine e la clausola che vi interessa è a pagina ventidue, ditelo: "guarda in particolare la sezione 7". Indicare dove guardare compensa l'attenzione che cala nel mezzo — di nuovo, esattamente come con un lettore umano.

## "Ma allora impara da quello che gli scrivo?"

È la domanda speculare, e merita una risposta netta: durante la conversazione sì, nel senso che abbiamo visto — rilegge tutto, quindi ogni cosa che scrivete orienta le risposte successive. Dopo, no. Il modello che risponde a voi stasera è identico, parametro per parametro, a quello che ha risposto a chiunque altro stamattina. Le vostre conversazioni non lo modificano.

L'addestramento — il processo che davvero cambia un modello — avviene altrove, prima, su grandi quantità di testo, e produce una nuova versione ogni qualche mese. Se e quali dati degli utenti finiscano in quel processo dipende dal contratto che avete col fornitore, ed è una questione seria ma separata: riguarda la riservatezza, non la memoria. Il modello non "si ricorda" del vostro contratto alla prossima conversazione in nessun caso; la domanda è semmai se il vostro contratto finisce nel mucchio da cui la versione dell'anno prossimo imparerà a scrivere contratti.

## Il rovescio della medaglia

Tutto questo ha anche un lato buono, che vale la pena dire: l'assenza di memoria è un azzeramento pulito. Un modello non si porta rancori da una conversazione all'altra, non resta ancorato all'idea sbagliata che si era fatto ieri, non ha il problema — umanissimo — di difendere oggi la posizione presa la settimana scorsa. Se una conversazione è partita male, la si butta e si riparte, e il modello riparte davvero.

Chi lavora bene con questi strumenti finisce per usare l'azzeramento come una risorsa: conversazioni corte, dedicate a una cosa sola, aperte e chiuse come si apre e si chiude una pratica. La chat infinita che contiene tutto — il lavoro, le prove, le curiosità della pausa pranzo — è comoda finché è corta e diventa il problema quando è lunga.

## Oggi esistono più memorie, e vanno distinte

Dire che «ogni conversazione riparte da zero» descrive bene il modello nudo, meno bene i prodotti del 2026. ChatGPT, Claude e gli agenti di coding possono conservare preferenze, cercare chat passate, mantenere file di istruzioni o recuperare note da archivi esterni. La memoria esiste a livello di prodotto; non è una facoltà uniforme del modello.

Conviene separare quattro meccanismi:

1. **finestra di contesto**: messaggi e materiali disponibili in questa esecuzione;
2. **memoria del prodotto**: fatti o preferenze salvati fra conversazioni;
3. **recupero esterno**: ricerca in file, database, repository o chat precedenti;
4. **stato del processo**: artefatti, checkpoint, test e decisioni conservati fuori dal modello.

La differenza è operativa. Un'informazione «salvata» non è necessariamente inserita in ogni richiesta; può essere recuperata solo quando un classificatore la ritiene pertinente. Un documento nel repository non occupa contesto finché l'agente non lo apre. Un checkpoint su disco sopravvive anche se cambiamo modello.

## La finestra lunga non elimina il problema

Centomila o un milione di token sembrano memoria sufficiente. Ma disponibilità e uso non coincidono. *Lost in the Middle* ha mostrato che modelli long-context possono sfruttare peggio informazione collocata in mezzo rispetto a inizio e fine. Lavori successivi hanno proposto meccanismi e addestramenti che riducono il problema, senza trasformare il contesto in un database perfetto.

Inoltre ogni token irrilevante compete per attenzione e può aumentare costo e latenza. Anthropic descrive il *context engineering* come la ricerca del più piccolo insieme di token ad alto segnale necessario al prossimo passo. È una definizione migliore di «mettere tutto nella chat».

## Memoria di progetto, non autobiografia della chat

Per un lavoro lungo mantengo un file breve con:

```text
Obiettivo e criterio di completamento
Vincoli e decisioni irreversibili
Architettura o struttura corrente
Fonti di verità
Decisioni prese con motivazione
Questioni aperte
Ultima verifica eseguita
```

La chat può contenere esplorazioni e ipotesi scartate. Il file contiene solo stato valido. Quando una decisione cambia, si aggiorna; non si aggiunge una seconda versione contraddittoria in fondo.

Per il software, codice e test sono memoria più affidabile della prosa. Per una ricerca, dataset, notebook e bibliografia. Per un articolo, scaletta, matrice fonti–affermazioni e bozza. L'agente deve poter ricostruire il punto del lavoro dagli artefatti.

## Compattare senza perdere il motivo

I sistemi compattano le conversazioni lunghe riassumendo messaggi vecchi. Il rischio è conservare la decisione e perdere il perché, oppure eliminare un'eccezione rara. Prima della compattazione conviene produrre un checkpoint strutturato:

- fatti verificati, con fonte;
- ipotesi ancora aperte;
- alternative scartate e ragione;
- file modificati;
- test eseguiti e test mancanti;
- prossima azione.

Non chiedete «riassumi la chat». Chiedete uno stato sufficiente a proseguire senza la chat. Sono oggetti diversi.

## Privacy e memoria persistente

Una funzione di memoria utile può conservare dettagli che non volevamo rendere permanenti. Le impostazioni, la possibilità di ispezionare e cancellare, il piano contrattuale e la retention contano. Non inserite segreti in una memoria solo perché evita di ripeterli. Credenziali e dati sensibili appartengono a sistemi dedicati con accessi e ciclo di vita controllati.

La regola è dare alla memoria il minimo necessario, con provenienza e scadenza. Una preferenza editoriale può durare; il nome di un cliente in un incidente corrente dovrebbe forse sparire a chiusura.

## Il test di ripresa

Chiudete la chat, apritene una nuova e fornite soltanto gli artefatti di progetto. Se l'agente non sa spiegare obiettivo, stato, vincoli e prossimo passo, la memoria del lavoro era nella conversazione sbagliata.

La chat è un tavolo. La memoria durevole sono gli oggetti che decidiamo di lasciare ordinati quando ci alziamo.

## La forma della macchina

La memoria che non c'è, insomma, non è un difetto da aggirare. È la forma della macchina. E come tutte le forme, appena la conosci ci lavori dentro meglio.

## Fonti e approfondimenti

- Liu et al., [Lost in the Middle](https://arxiv.org/abs/2307.03172), 2023.
- Zhang et al., [Found in the Middle](https://arxiv.org/abs/2406.16008), su mitigazioni della dipendenza dalla posizione.
- Anthropic, [Effective context engineering for AI agents](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents), 2025.
- OpenAI, [Memory FAQ](https://help.openai.com/en/articles/8590148-memory-faq), funzioni e controlli correnti del prodotto.
- Anthropic, [How Claude remembers your project](https://docs.anthropic.com/en/docs/claude-code/memory), istruzioni persistenti e gerarchia dei file.
