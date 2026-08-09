---
title: I modelli a pesi aperti, spiegati senza mitologia
description: "Open source" applicato a un modello di AI vuol dire una cosa diversa da quella a cui siamo abituati col software. Cosa si scarica davvero, cosa cambia nel lavoro quotidiano, quanto costa, e quando conviene.
date: 2026-07-07
author: vincenzo
tags: [modelli aperti, open source, LLM, infrastruttura]
image: /images/posts/cover-pesi-aperti.png
lang: it
---

![I modelli a pesi aperti](/images/posts/cover-pesi-aperti.png)

Che cosa contiene, esattamente, il file che scaricate quando prendete un modello "aperto"; perché la parola presa in prestito dal software libero qui promette più di quanto mantenga; quanto costa davvero tenerselo in casa contro un abbonamento; e il collaudo di un pomeriggio per scoprire, sul vostro lavoro, dove passa oggi il confine.

Ogni volta che esce un modello "open source" parte la stessa discussione, e quasi sempre parte storta. Da una parte chi annuncia che ormai non serve più pagare nessuno, dall'altra chi liquida tutto come giocattoli per smanettoni. Sono sbagliate tutte e due, e per lo stesso motivo: si sta usando una parola presa in prestito da un mondo dove significava un'altra cosa.

Vale la pena rimettere in fila i fatti, perché la decisione se usare questi modelli o no ha conseguenze concrete — sui costi, sulla riservatezza dei documenti, su cosa succede il giorno in cui un fornitore cambia idea — e va presa sapendo cosa si sta comprando. O meglio, cosa si sta scaricando.

## Cosa si scarica, esattamente

Quando scaricate un modello a pesi aperti — Llama, Mistral, Qwen, Gemma, DeepSeek, e la lista si allunga ogni pochi mesi — ottenete un file di numeri. Molti numeri: da qualche miliardo a qualche centinaio di miliardi. Sono i **pesi**, i parametri che il modello ha aggiustato durante l'addestramento, e sono letteralmente tutto ciò che il modello "sa": dentro quella matassa di cifre stanno l'inglese, l'italiano, la chimica, lo stile delle email commerciali e il modo in cui si chiude una lettera formale in giapponese.

Con quel file e un programma che lo sa eseguire, il modello gira sul vostro computer. Senza abbonamento, senza connessione, senza che nessuno veda cosa gli scrivete. Potete spegnerlo, copiarlo, tenerlo su un disco in cassaforte. Fra dieci anni funzionerà identico, cosa che di nessun servizio in cloud si può dire.

Quello che *non* ottenete è tutto il resto: i dati su cui è stato addestrato, il codice che ha condotto l'addestramento, il registro delle scelte fatte strada facendo. Nel software libero classico, "sorgente aperto" significa che puoi leggere come è fatto un programma e ricostruirlo da zero. Qui puoi eseguirlo e modificarlo ai margini — perfino riaddestrarlo un poco sui tuoi documenti, si chiama *fine-tuning* — ma non puoi rifarlo, e non puoi sapere fino in fondo cosa ci sia dentro. È come ricevere una torta con il permesso di mangiarla, congelarla e aggiungerci la glassa: senza la ricetta, e senza la lista degli ingredienti.

Per questo la formula onesta è **pesi aperti**, non open source. E prima di adottarne uno in azienda c'è sempre un documento da leggere: la licenza. Alcune sono davvero libere; altre mettono paletti — limiti sull'uso commerciale sopra una certa scala, divieti su interi campi di impiego, obblighi di menzione. Sono due pagine, e vanno lette prima, non dopo.

## Cosa cambia nel lavoro

Il punto pratico è uno, e conviene guardarlo dritto: **dove girano i vostri documenti**.

Con un servizio in cloud, ogni file che caricate esce dal vostro computer e viene elaborato sulla macchina di qualcun altro. Esistono contratti che regolano cosa il fornitore può farne, e alcuni sono buoni contratti. Ma restano contratti: proteggono nella misura in cui vengono rispettati, e nella misura in cui qualcuno da voi ha letto la clausola giusta prima di firmare.

Con un modello locale la domanda non si pone proprio. Il testo entra nella memoria del vostro computer ed esce, al massimo, dalla vostra stampante. Per uno studio che tratta atti, referti, bilanci non ancora depositati, questa non è una sfumatura tecnica: è la differenza fra dover *fidarsi* e non doverlo fare.

Poi c'è il conto della serva, che merita di essere fatto per esteso. Un abbonamento serio costa fra i venti e i trenta euro al mese a persona: per uno studio di cinque, fa fra i milleduecento e i milleottocento euro l'anno, ogni anno. Un computer capace di far girare bene un modello di taglia media — sui portatili recenti con memoria unificata ci si arriva senza esotismi — costa fra i millecinquecento e i tremila euro, una volta. Il pareggio arriva presto, *se* il modello locale basta per il lavoro che fate. Ed è un "se" vero, non retorico: dipende dal punto seguente.

## Cosa non cambia, e conviene sapere

Un modello aperto da trenta miliardi di parametri non è un modello da frontiera, e la distanza non è marketing. Sulle cose ordinarie — riassumere, riformulare, estrarre dati da un documento, tradurre, classificare — la differenza si nota poco o niente. Su un ragionamento lungo, su un problema che richiede di tenere insieme molti vincoli, su codice non banale, la differenza si nota eccome, e nessuna configurazione la cancella.

L'errore più comune che vedo è il collaudo sbagliato: si prova il modello locale sul compito più difficile che si ha, lo si vede arrancare, e si conclude che i modelli aperti non servono. È come giudicare un'utilitaria mettendola in salita col rimorchio. Il confronto sensato è un altro: **questa cosa specifica, che devo fare tutti i giorni, la fa abbastanza bene?** Per molte attività d'ufficio la risposta è sì da tempo — e allora ogni documento che passa di lì è un documento che non è uscito dallo studio.

L'altro costo che nessuno mette in conto è la manutenzione. Il modello va scaricato e prima o poi sostituito da uno migliore; il programma che lo esegue si aggiorna; ogni tanto qualcosa smette di funzionare per motivi suoi. Niente di drammatico — parliamo di ore l'anno, non di giornate — ma se in studio non c'è una persona a cui questa attività non dispiace, diventerà il fastidio di qualcuno che non l'ha chiesto. È il criterio più affidabile che conosco per decidere: non "abbiamo l'hardware?", ma "abbiamo la persona?".

## Come si prova, senza impegnarsi

Servono un pomeriggio e zero acquisti.

Si installa uno dei programmi che rendono la cosa banale — **Ollama** o **LM Studio**, si scaricano e si aprono come qualsiasi applicazione — e si scarica un modello di taglia media, fra i sette e i quattordici miliardi di parametri: su un computer recente parte senza storie. Poi si prende **il lavoro vero**: non l'esempio inventato per il test, ma cinque documenti di quelli che trattereste domattina, anonimizzati quanto serve.

E si fa la gara: stessa richiesta al modello locale e al servizio cloud che usate di solito, risultati affiancati. La domanda non è "quale è più brillante" ma "questo qui è utilizzabile, per questa cosa qui?". Se sì, avete appena tolto una categoria di documenti dal cloud e imparato quanto vale il vostro caso specifico. Se no, avete perso un pomeriggio e guadagnato una cosa che vale altrettanto: sapere dove passa il confine, oggi, per il vostro lavoro.

## Perché la cosa conta anche se non li userete mai

Molti, fatta la prova, resteranno sul cloud — per ottime ragioni: modelli migliori, zero manutenzione, comodità. Ma l'esistenza dei modelli aperti lavora anche per loro, in silenzio.

Sono il pavimento del mercato. Fissano il livello sotto il quale non ha senso pagare, e costringono chi vende a valere la differenza. E sono la risposta alla domanda che ogni dipendenza da fornitore dovrebbe avere pronta: *e se domani?* Se domani il prezzo raddoppia, se il servizio chiude, se le condizioni cambiano, se un aggiornamento rompe il flusso che usate da un anno — la strada di riserva esiste, è percorribile, e sapere che esiste cambia il potere contrattuale anche di chi non la imbocca.

## Aperto rispetto a che cosa

Nel software classico, open source consente di studiare, modificare e distribuire il codice secondo una licenza. Un sistema di AI aggiunge dati, codice di training, parametri, architettura e procedure di valutazione. Pubblicare soltanto i pesi rende possibile l'inferenza e spesso il fine-tuning, ma non ricostruisce necessariamente il sistema.

La Open Source AI Definition dell'OSI richiede libertà di uso, studio, modifica e condivisione e informazioni sufficienti sui dati, oltre a codice e parametri. Per questo è utile dire **open weights** quando è esattamente ciò che abbiamo: evita di importare una garanzia che la licenza o la documentazione non offrono.

## Licenza, policy e provenienza

Due modelli scaricabili possono avere libertà molto diverse. Uno usa Apache 2.0; un altro limita settori, dimensione dell'organizzazione o uso commerciale; un terzo accompagna la licenza con una policy d'uso separata. Controllate:

- licenza dei pesi e del codice;
- condizioni su output e modelli derivati;
- obblighi di attribuzione o redistribuzione;
- acceptable use policy;
- licenze di tokenizer, dataset e componenti;
- restrizioni dei modelli incorporati nel workflow.

GPT-OSS, per esempio, è pubblicato da OpenAI con pesi e licenza Apache 2.0 insieme a una usage policy e a un model card. È molto più informativo dell'etichetta «aperto» presa da sola.

## Il costo vero dell'esecuzione

I pesi gratuiti non rendono gratuita l'inferenza. Servono download, storage, RAM/VRAM, energia, tempo operativo e aggiornamenti. Il costo dipende da precisione e quantizzazione, lunghezza del contesto, batch, throughput e latenza richiesta.

Per un uso saltuario, una API può essere più economica di una GPU accesa. Per carico continuo e prevedibile, hardware posseduto o istanze noleggiate possono vincere. Per dati sensibili, il valore del controllo può dominare il conto.

Misurate costo per esito accettato includendo setup, retry e revisione. Un modello più piccolo che sbaglia campi critici è costoso anche se produce token quasi gratis.

## Quantizzazione e qualità

Ridurre i bit dei pesi permette di eseguire modelli grandi su hardware più piccolo. La perdita non è uniforme: alcuni compiti e layer sono più sensibili; formati e runtime implementano compromessi diversi. «4-bit» non è un benchmark.

Testate sul vostro set con identico prompt e criteri. Misurate qualità, token al secondo, memoria e stabilità su contesti lunghi. Conservate modello esatto, quantizzazione e runtime: il nome della famiglia non basta a riprodurre il risultato.

## Controllo non significa sicurezza automatica

Eseguire localmente impedisce al provider di inferenza di ricevere prompt e output. Restano vulnerabilità del runtime, custom code, modelli malevoli, telemetria, download, backup e accesso fisico. Inoltre un modello locale non riceve automaticamente patch di sicurezza o miglioramenti dei filtri.

Il vantaggio è la possibilità di scegliere e congelare. La responsabilità di aggiornare, isolare e monitorare passa all'operatore.

## Il valore strategico: sostituibilità

Un'architettura sana separa l'applicazione dal modello. Definite un contratto di input/output, una suite di eval, un registro di versioni e una fallback. Così potete confrontare modello cloud, open-weight locale e GPU remota senza riscrivere il prodotto.

La portabilità non è completa se il prompt dipende da idiosincrasie del provider o il workflow usa strumenti proprietari. Va testata: eseguite periodicamente un campione sul modello alternativo e misurate il divario.

## Quando convengono

I pesi aperti sono forti quando servono:

- dati sotto controllo diretto;
- comportamento congelabile e versionato;
- personalizzazione profonda;
- alto volume stabile;
- funzionamento offline o edge;
- ricerca su rappresentazioni e inferenza;
- indipendenza da una sola API.

Sono meno attraenti quando il team non vuole gestire infrastruttura, il carico è intermittente, il modello frontier è decisamente migliore sul task o servono tool e supporto gestiti.

## Un benchmark di un pomeriggio fatto bene

Preparate 30–50 casi anonimizzati, con risposte attese o criteri. Confrontate almeno un modello gestito e uno open-weight. Registrate qualità cieca, errori critici, latenza, memoria, costo, facilità di integrazione e licenza. Provate un contesto realistico, non la domanda promozionale più breve.

Ripetete ogni sei o dodici mesi. Il risultato non è «chi vince» in astratto: è il prezzo corrente della vostra possibilità di uscita.

## Un pomeriggio all'anno

Per questo il consiglio che do più spesso non è "passate ai modelli aperti". È più piccolo e più utile: provatene uno una volta l'anno, un pomeriggio, sui vostri documenti. Non per adottarlo — per sapere dov'è arrivato il pavimento. Chi fa questa prova regolarmente prende decisioni migliori anche sul cloud: sa cosa sta comprando, perché ha visto cosa c'è gratis.

## Fonti e approfondimenti

- Open Source Initiative, [Open Source AI Definition](https://opensource.org/ai/open-source-ai-definition), versione corrente.
- OSI, [Open Source AI FAQ](https://opensource.org/ai/faq), distinzione fra componenti e libertà richieste.
- OpenAI, [gpt-oss model card](https://openai.com/index/gpt-oss-model-card/), esempio documentato di modello open-weight.
- Hugging Face, [Model Cards](https://huggingface.co/docs/hub/model-cards), provenienza, licenze e limitazioni.
- NIST, [AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework), valutazione e governance.
