---
title: Come si chiede a un'AI un sito web fatto bene
description: Il primo tentativo esce sempre uguale a mille altri, e il motivo non è il modello. Cosa contiene davvero una richiesta generica, in che ordine si lavora, e le tre regole che separano un sito che regge da uno che si sfalda.
date: 2026-07-28
author: vincenzo
tags: [prompt engineering, web, metodo, laboratorio]
image: /images/posts/cover-prompt-di-un-sito.png
lang: it
---

![Il prompt di un sito](/images/posts/cover-prompt-di-un-sito.png)

Perché una richiesta generica produce sempre lo stesso sito; le tre cose che, messe nella richiesta, lo spostano davvero; l'ordine in cui conviene procedere per non ritrovarsi con un blocco impossibile da correggere; e la differenza fra chiedere modifiche e dettare regole, che è quella fra un sito che dura e uno che si sfalda alla terza mano.

Chiedete a un modello «fammi un sito per il mio studio, moderno e professionale» e otterrete un sito. Funziona, si apre sul telefono, ha le sezioni al posto giusto. E somiglia a tutti gli altri: gradiente viola, tre riquadri affiancati con le icone, un bottone che dice "Scopri di più", una foto di persone sorridenti attorno a un tavolo che non esistono.

La tentazione è dare la colpa al modello. Ma il modello ha fatto esattamente il suo lavoro: davanti a una richiesta senza informazione, ha restituito **la media di tutto quello che ha visto**. E la media dei siti web del mondo è precisamente quella cosa lì — il gradiente, le icone, i sorrisi. Non è un difetto della macchina; è lo specchio fedele di una richiesta vuota.

Il lavoro, allora, non è trovare le parole magiche. È mettere nella richiesta qualcosa che la media non ha. Questo articolo è il procedimento che uso io, maturato costruendo siti veri — incluso quello che state leggendo.

## Le tre cose che spostano il risultato

**Un riferimento vero, non aggettivi.** "Moderno", "pulito", "elegante" non significano niente: per il modello sono esattamente le parole che accompagnavano il gradiente viola. Un indirizzo invece è informazione densa: «guarda com'è impaginato *questo* sito — colonna singola, molto bianco, titoli in un serif da giornale, un solo colore d'accento usato con parsimonia. Voglio quella famiglia di scelte, non quel sito». Un riferimento buono vale cinquanta righe di descrizione, perché non descrive il gusto: lo *mostra*.

**Vincoli che escludono.** Dire cosa non volete restringe più che dire cosa volete, perché ogni divieto amputa una fetta intera di quella media. «Niente gradienti. Niente icone decorative. Niente animazioni all'ingresso. Nessuna frase che dica al lettore quanto siamo bravi: se siamo bravi si deve vedere da come è scritto il resto.» Quattro divieti, e il sito medio è già diventato impossibile.

**Il contenuto vero.** È il punto che salta sempre, ed è il più pesante di tutti. Un sito costruito su testo segnaposto esce con le proporzioni sbagliate — il finto ha sempre la lunghezza comoda, il vero mai — e soprattutto rimanda il problema: prima o poi i testi andranno scritti, e scoprirete che la struttura non li contiene. Dategli i titoli veri, i paragrafi veri, i nomi veri delle sezioni. Se non esistono ancora, scriveteli *prima*: è l'ora meglio spesa dell'intero progetto, e costringe a decidere cosa il sito deve dire — che era la domanda vera fin dall'inizio, nascosta sotto quella sul colore dei bottoni.

## L'ordine dei passaggi

L'errore più costoso è chiedere tutto insieme. «Fammi il sito» produce un blocco monolitico dove ogni correzione ne sposta altre tre, e dopo cinque giri di modifiche nessuno — né voi né il modello — sa più perché una cosa è fatta così.

Conviene lavorare per strati, e chiudere ogni strato prima di aprire il successivo.

Prima **la struttura**: quali pagine, cosa contiene ciascuna, in che ordine, cosa deve fare il lettore alla fine di ognuna. Niente codice — un elenco puntato. È il momento in cui si scoprono le cose mancanti ("e i contatti dove stanno?") ed è il momento giusto per scoprirle, quando spostarle costa una riga.

Poi **i testi**, uno per volta, ognuno approvato prima del successivo. Un sito con la struttura giusta e i testi mediocri è un sito mediocre: questa fase merita la metà del tempo totale, e nessuno gliela dà mai.

Poi **il linguaggio visivo**, dichiarato in numeri e non in aggettivi: due caratteri tipografici e basta, una scala di dimensioni precisa, un colore d'accento col suo codice esadecimale, i raggi degli angoli, una scala di spaziature. Sono venti righe. Il modello le applicherà con una coerenza che nessun "rendilo più armonioso" otterrà mai, perché adesso *armonioso* ha una definizione.

Solo alla fine **il codice**, pagina per pagina, guardando il risultato dopo ognuna. Mai due pagine senza aver guardato la prima.

## La regola dei sistemi, non delle pagine

Qui sta la differenza fra un sito che regge nel tempo e uno che si sfalda alla terza modifica, ed è una differenza di *come si chiede*.

«Fai questo titolo un po' più piccolo» produce un titolo più piccolo — e un'eccezione. Dieci richieste così producono dieci eccezioni, cioè un sito dove ogni pagina è un caso a sé. «Definisci una scala tipografica e usala ovunque; nessuna dimensione fuori scala» produce una **regola**, e la regola vale anche fra sei mesi, anche per la pagina che non esiste ancora, anche per la persona — o il modello — che ci metterà mano dopo di voi.

Vale per tutto: spaziature, colori, ombre, comportamenti al passaggio del mouse. Ogni volta che state per chiedere una correzione puntuale, fermatevi un secondo e chiedetevi se non state guardando il sintomo di una regola mancante. Il salto di qualità del lavorare con un modello è tutto qui: smettere di ordinare modifiche e cominciare a dettare principî. Il modello è uno straordinario esecutore di principî — è l'unico collaboratore che, data una regola, la applica *davvero* ovunque.

## Guardare, non leggere

Un modello non vede quello che produce. Scrive codice che *secondo lui* produrrà un certo effetto, e ha ragione spesso — ma non sempre, e i casi in cui ha torto sono invisibili dal codice.

Quindi: dopo ogni passaggio si apre la pagina e si guarda. Su schermo grande e sul telefono, con il tema chiaro e con quello scuro se c'è. E quando qualcosa non va, si descrive **quello che si vede**, non quello che si prova: «il titolo va a capo dopo due parole e l'ultima riga resta orfana» è un'informazione su cui il modello può agire; «il titolo non mi convince» lo rimanda a indovinare, cioè alla media, cioè al punto di partenza.

Ancora meglio: mandategli la schermata. I modelli attuali le leggono, e la differenza è quella fra un architetto che ragiona sulla pianta e uno che è entrato nella stanza. Buona parte delle correzioni di questo sito è passata da screenshot commentati, e il commento era spesso una freccia e tre parole.

## Il pezzo che nessuno chiede

Alla fine, quando il sito piace, resta la richiesta più preziosa di tutte, quella che non fa quasi nessuno: **fatevi spiegare come è fatto**.

Come sono organizzate le cartelle. Dove si cambia un colore, dove si aggiunge un articolo, quale file non va toccato mai. Cosa succede quando si pubblica. Dieci minuti di domande, e le risposte salvate accanto al progetto.

Senza questo, avete un sito che funziona finché non serve cambiarlo — e al primo cambiamento tornate a dipendere da qualcuno, fosse anche dallo stesso modello, ripartendo però da zero contesto. Con questo, avete una cosa vostra: la potete mantenere, migliorare, e all'occorrenza spiegare al prossimo che ci lavora.

Che poi era il punto. Il sito medio si compra a poco dappertutto. Quello che non si compra è un sito che è vostro due volte — nelle scelte, perché le avete fatte voi; e nella manutenzione, perché sapete dove mettere le mani.
