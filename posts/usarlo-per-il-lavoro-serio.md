---
title: Si può usare per il lavoro serio?
description: Sì, con lo stesso trattamento che riservereste a un collaboratore nuovo e bravo: fiducia proporzionata, verifica sistematica, e chiarezza su chi firma. Il protocollo, in pratica.
date: 2026-03-31
author: vincenzo
tags: [metodo, verifica, professioni]
image: /images/posts/cover-usarlo-per-il-lavoro-serio.png
lang: it
---

![Si può usare per il lavoro serio?](/images/posts/cover-usarlo-per-il-lavoro-serio.png)

Qual è il modello mentale giusto per capire quanta fiducia dare, come si costruisce una verifica che non annulli il risparmio di tempo, dove sta il confine oltre il quale non si delega, e le due regole che uno studio dovrebbe darsi prima di cominciare invece che dopo.

La domanda vera sotto questa domanda è: mi posso fidare? E la risposta è la stessa che dareste per una persona: **dipende da cosa, e comunque si controlla**.

## Il collaboratore nuovo

Il modello mentale che funziona meglio è questo: avete assunto qualcuno di sveglio, colto, velocissimo, che ha letto una quantità sterminata di roba, non conosce il vostro studio, non ha mai visto un vostro cliente, non risponde di niente, e ogni tanto sbaglia con assoluta sicurezza.

A una persona così cosa affidereste? Sicuramente una prima stesura. Una ricerca preliminare. Un riassunto di quaranta pagine da controllare. Un confronto fra due versioni di un contratto. Sicuramente non la firma, non la decisione sul caso limite, non la telefonata al cliente arrabbiato.

E in ogni caso rileggereste, all'inizio tutto e poi a campione crescente man mano che imparate dove sbaglia.

Questo modello mentale è più utile di qualsiasi elenco, perché si adatta ai casi che l'elenco non prevede.

## Verificare senza perdere il vantaggio

L'obiezione ovvia: se devo controllare tutto, tanto vale farlo io. È giusta solo se si controlla male.

Il controllo efficiente è **selettivo**, e si concentra dove il modello sbaglia — che sono posti precisi.

I **numeri**: qualunque cifra, data, importo, percentuale va riscontrata sulla fonte. È il punto debole strutturale, e per fortuna è veloce da controllare.

I **riferimenti**: articoli, norme, sentenze, citazioni, indirizzi. Se sono inventati, lo sono in modo plausibile. Ogni riferimento va aperto, non riconosciuto a vista.

Le **negazioni e le eccezioni**: "salvo che", "non si applica quando". Sono i punti dove un errore ribalta il senso e la lettura distratta non lo coglie.

Quello che **non** c'è: il modello omette in silenzio. Nella sintesi di un contratto la clausola che manca non lascia buchi visibili.

La prosa, la struttura, la scorrevolezza: quelle si possono leggere in fretta. Il tempo va speso dove sta il rischio, non distribuito uniformemente.

## Il confine

C'è un criterio secco che uso per decidere se una cosa si delega: **se il risultato è sbagliato e nessuno se ne accorge, cosa succede?**

Se la risposta è "lo vede il destinatario e chiede chiarimenti", si delega tranquillamente. Se la risposta è "finisce in un atto", "va in scadenza", "il cliente ci si basa per una decisione", allora si delega la stesura ma non il controllo, e il controllo lo fa chi sa.

L'errore che vedo più spesso non è delegare troppo. È delegare senza decidere: usare il modello per una cosa importante senza aver stabilito prima chi la rilegge e con che criterio. Il risparmio di tempo evapora nel dubbio.

## Le due regole da darsi prima

**Una riga su chi firma.** Quello che esce da un modello ed entra in un documento vostro è vostro, con tutte le conseguenze. Sembra ovvio e non lo è: nei momenti di fretta la tentazione di considerare la macchina corresponsabile esiste, ed è una tentazione che va disinnescata prima, non dopo.

**Una riga su cosa non passa di lì.** Quali categorie di documenti non vanno caricate su un servizio esterno. Senza una regola scritta la decisione la prende ogni volta chi ha fretta, e chi ha fretta decide male.

Sono due righe. In uno studio che le ha scritte, il resto si sistema da sé; in uno che non le ha, ogni caso è una discussione.

## Il vero rischio

Non è che il modello sbagli — sbaglia, e lo si sa. È che smetta di sbagliare abbastanza spesso da farvi abbassare la guardia.

## Serio significa definire il danno

La stessa percentuale di errore ha conseguenze diverse. Un titolo mediocre richiede una riscrittura; una dose medica errata può ferire; una clausola omessa può spostare responsabilità economica. Prima di scegliere modello e prompt bisogna classificare il rischio.

Uso quattro livelli:

1. **esplorativo**: l'output genera opzioni, nessuno lo usa come fatto;
2. **assistito**: una persona competente controlla ogni risultato;
3. **operativo**: il sistema agisce entro vincoli, con test e rollback;
4. **critico**: danni rilevanti o diritti; servono governance, validazione e responsabilità formale.

Il livello determina dati ammessi, grado di autonomia, evidenze, logging e approvazioni. Non esiste un prompt che trasformi un processo di livello quattro in un giocattolo sicuro.

## La scheda dell'incarico

Un collaboratore nuovo riceve mandato, materiali e definizione di completamento. Fate lo stesso:

```text
Decisione supportata:
Destinatario e uso previsto:
Fonti ammesse e data di validità:
Azioni vietate senza approvazione:
Formato di consegna:
Controlli automatici:
Revisore competente:
Condizioni di escalation:
Traccia da conservare:
```

La voce «uso previsto» impedisce riusi pericolosi. Un riassunto per orientare una riunione non diventa, solo perché ben scritto, un parere da inviare al cliente.

## Fiducia calibrata per componente

Non si assegna una fiducia unica al «modello». Si valuta una pipeline. L'estrazione può essere affidabile e il ragionamento debole; il calcolo corretto e la fonte obsoleta; la bozza ottima e la citazione inventata.

Scomponete e collegate a ogni passaggio un controllo:

| Passaggio | Controllo |
|---|---|
| acquisizione documenti | completezza, checksum, versione |
| estrazione | campione contro originale, coordinate pagina |
| classificazione | set di test e matrice degli errori |
| calcolo | runtime deterministico e invarianti |
| sintesi | copertura delle affermazioni chiave |
| pubblicazione/azione | approvazione e rollback |

La verifica deve produrre evidenza. «Ho ricontrollato» è un'altra frase generata.

## Gestire eccezioni e cambiamenti

Le demo usano casi puliti. Il lavoro serio contiene scansioni storte, campi mancanti, lingue miste, versioni contraddittorie e richieste fuori perimetro. Il sistema deve saper dire «non processabile» e instradare a una persona.

Ogni aggiornamento di modello, prompt, parser o fonte può cambiare il comportamento. Conservate un set di regressione con casi ordinari, limiti ed errori storici. Eseguitelo prima del rilascio e monitorate in produzione segnali di deriva: aumento dei retry, distribuzione delle confidenze, campi mancanti, correzioni umane.

## Dati e fornitori

Il piano consumer, l'API e un contratto enterprise possono avere condizioni diverse su addestramento, retention e controlli. OpenAI dichiara di non usare per addestramento i dati di API e prodotti business per impostazione predefinita; Anthropic applica condizioni specifiche ai prodotti commerciali e offre accordi di zero data retention per servizi qualificati. Queste frasi non sostituiscono una valutazione del vostro flusso.

Mappate controller, processor, regione, subprocessor, log, backup, strumenti chiamati e durata. Una chat può rispettare la policy mentre un connettore invia il documento altrove. Minimizzate dati e privilegi.

## Chi firma deve poter spiegare

L'accountability non richiede che una persona ripeta internamente ogni token. Richiede che comprenda fonte, metodo, limiti e criterio con cui il risultato è stato accettato. Se il revisore non possiede competenza o tempo, l'etichetta «human in the loop» è decorativa.

Per gli output importanti conservate una *decision record*: input, versione, fonti, controlli, eccezioni, approvatore. Non tutto per sempre; secondo retention proporzionata.

## Il protocollo minimo

1. scegliere un task circoscritto;
2. misurare baseline umana;
3. definire rischio e fallimenti inaccettabili;
4. progettare controlli indipendenti;
5. fare shadow mode senza effetti esterni;
6. confrontare qualità, rework e costo;
7. introdurre autonomia per gradi;
8. monitorare e riesaminare dopo aggiornamenti.

Usare l'AI per lavoro serio è ingegneria di processo. Il modello è una componente straordinariamente flessibile; proprio per questo i confini devono essere meno flessibili.

## Come le cinture

Dopo tre mesi in cui il riassunto è sempre venuto bene, la lettura di controllo si fa distratta. È il momento in cui arriva il riassunto sbagliato, e nessuno lo vede. La contromisura non è la diffidenza permanente, che non regge: è tenere il controllo dei numeri e dei riferimenti come un gesto meccanico, che non richieda di essere motivati. Come le cinture: non le si mette perché si teme l'incidente.

## Fonti e approfondimenti

- NIST, [AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework), quadro volontario per gestione del rischio.
- OpenAI, [Business data privacy, security, and compliance](https://openai.com/business-data/), impegni correnti sui dati commerciali.
- Anthropic, [How long do you store my organization's data?](https://privacy.anthropic.com/en/articles/7996866-how-long-do-you-store-my-organization-s-data), retention dei prodotti commerciali.
- Anthropic, [Zero data retention](https://privacy.anthropic.com/en/articles/8956058-i-have-a-zero-data-retention-agreement-with-anthropic-what-products-does-it-apply-to), ambito degli accordi ZDR.
- ILO, [Generative AI and Jobs](https://www.ilo.org/publications/generative-ai-and-jobs-refined-global-index-occupational-exposure), 2025.
