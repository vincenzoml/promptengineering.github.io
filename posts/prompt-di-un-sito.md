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

## Prima del layout viene la funzione

«Fammi un sito moderno» porta a hero, gradiente, tre card e call to action perché è la risposta statisticamente comune. Una specifica professionale parte da persone e decisioni:

- chi arriva e da quale canale;
- che cosa deve capire nei primi trenta secondi;
- quale azione deve poter completare;
- quale prova riduce il dubbio;
- quali contenuti cambieranno spesso;
- chi li manterrà;
- quali vincoli legali, tecnici e di accessibilità esistono.

La homepage non è l'intero sito. Disegnate prima mappa dei contenuti e percorsi principali. Se un lettore deve confrontare servizi, leggere casi e contattare l'azienda, ogni passaggio ha informazione e stato propri.

## Fornire materiale vero

Il modello inventa testimonial e metriche quando il brief chiede «social proof» ma non contiene prove. Date testi, immagini, identità visiva, casi, vincoli e fonti. Segnate ciò che può essere riscritto e ciò che deve restare letterale.

Un inventario iniziale:

```text
Contenuti approvati
Claim con relativa prova
Asset e diritti d'uso
Pagine obbligatorie
Azioni e destinazioni
Dati raccolti dai form
Lingue e mercati
Elementi ancora mancanti
```

Se manca un claim, il sito deve mostrare un placeholder o ometterlo, non fabbricarlo.

## Specificare un sistema visivo

Un'immagine di riferimento vale più di «minimal». Ma chiedete al modello di estrarne regole, non copiarla: scala tipografica, spaziatura, griglia, raggi, contrasto, densità, comportamento responsive, trattamento di immagini e stati interattivi.

Definite token di design:

- colori semantici, non `blue-500` sparsi;
- font e fallback;
- scala di spaziatura;
- larghezze e breakpoint;
- componenti e varianti;
- focus, hover, errore, loading e vuoto.

La coerenza nasce da poche regole riutilizzate, non dal prompt che dice «mantieni coerenza».

## Accessibilità come criterio di accettazione

WCAG 2.2 offre requisiti testabili: contrasto, tastiera, focus visibile, target size, alternative testuali, etichette, struttura semantica. Inseriteli nella specifica e nei test.

Un controllo minimo comprende:

1. navigazione completa da tastiera;
2. ordine di focus e skip link;
3. heading gerarchici;
4. label e messaggi dei form;
5. contrasto e zoom al 200%;
6. `prefers-reduced-motion`;
7. screen reader su percorsi chiave.

Lighthouse o axe trovano una parte degli errori; non dimostrano usabilità. Il test manuale rimane.

## Prestazioni: budget prima delle animazioni

Core Web Vitals misura aspetti osservabili dell'esperienza: LCP per caricamento principale, INP per reattività, CLS per stabilità. Fissate un budget su mobile reale:

- JavaScript iniziale;
- peso immagini e font;
- numero di richieste;
- soglie CWV al percentile 75;
- nessuna dipendenza client quando HTML e CSS bastano.

L'AI tende ad aggiungere librerie perché rendono semplice generare il codice. Ogni dipendenza deve giustificare peso, manutenzione e superficie di sicurezza.

## Il prompt deve includere l'ambiente

Indicate framework e versione, package manager, convenzioni, browser supportati, strategia di rendering, CMS, analytics e deployment. Prima di cambiare codice, l'agente deve leggere istruzioni del repository e componenti esistenti.

Per una modifica:

```text
Implementa la pagina dentro il design system esistente.
Non introdurre dipendenze senza motivazione.
Riusa componenti e token; conserva URL e analytics.
Prima scrivi test/criteri per accessibilità e responsive.
Alla fine esegui build, test e audit; mostra il diff rilevante.
```

## Dalla demo al prodotto

Una demo felice ignora stati che occupano metà del lavoro reale:

- loading lento e retry;
- zero risultati;
- testo molto lungo o tradotto;
- immagini mancanti;
- errore del form;
- autenticazione scaduta;
- consenso e preferenze;
- 404, redirect e metadata social;
- stampa, condivisione e deep link.

Chiedete una matrice stato–componente e verificatela. Un sito che regge il contenuto peggiore è più vicino alla produzione di uno screenshot perfetto.

## Sicurezza e dati

Non inserite chiavi nel frontend. Validate input sul server, proteggete form da abuso, minimizzate analytics e documentate cookie. Le dipendenze generate devono essere controllate; il codice non diventa sicuro perché compila.

Per siti con CMS, definite chi può pubblicare, anteprima, versioni e rollback. Per contenuti AI, mantenete fonti e responsabilità editoriale.

## Il brief completo, progressivo

1. obiettivo e utenti;
2. mappa e contenuti reali;
3. riferimenti e regole visive;
4. stack e vincoli;
5. criteri per accessibilità, performance, SEO e sicurezza;
6. componenti e stati;
7. piano di implementazione incrementale;
8. verifiche automatizzate e manuali;
9. handover e manutenzione.

Fate approvare ogni strato prima di generare il successivo. Correggere una mappa costa minuti; correggere lo stesso errore dopo venti pagine costa giorni.

## Un sito vostro due volte

Che poi era il punto. Il sito medio si compra a poco dappertutto. Quello che non si compra è un sito che è vostro due volte — nelle scelte, perché le avete fatte voi; e nella manutenzione, perché sapete dove mettere le mani.

## Fonti e approfondimenti

- W3C, [Web Content Accessibility Guidelines 2.2](https://www.w3.org/TR/WCAG22/), standard di accessibilità.
- web.dev, [Web Vitals](https://web.dev/articles/vitals), metriche e soglie correnti.
- MDN, [Responsive design](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design), riferimento tecnico.
- OWASP, [Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/), requisiti di sicurezza.
- W3C, [HTML specification](https://html.spec.whatwg.org/), semantica e comportamento.
