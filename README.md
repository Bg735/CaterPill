# CaterPill
CaterPill è un dispenser intelligente di pillole medicinali, ideato per rendere semplici e intuitive la pianificazione e la gestione dei periodi di assunzione di medicinali.
Il sistema fornisce un'interfaccia grafica per registrare un piano mensile di assunzione di medicinali, e può ospitare fino a tre diverse tipologie di pillole (collezionate in stack indipendenti), implementando un gestore dell'inventario che tiene traccia, in vece dell'utente, delle quantità di pillole disponibili, della necessità di rimpinguare i serbatoi e della scadenza dei medicinali immagazzinati.
Grazie ai sistemi di segnalazione acustica e notifica grafica, CaterPill garantisce che l'utente non dimentichi mai gli orari di assunzione, consentendo eventualmente di posticipare l'erogazione ad un momento successivo della giornata {o saltare l'erogazione per la giornata corrente}.

#### Business Flow
-  ***Riempimento***
>Dall'interfaccia, l'utente entra nella schermata dell'inventario. Per lo stack scelto, seleziona l'opzione "*Riempi*". A questo punto, lo stack d'interesse viene allineato con l'ingresso, la bocchetta superiore si apre e inizia il processo di riempimento.
>La schermata propone il tasto di fine riempimento, accostato al contatore di pillole complessive presenti nello stack; quando il pulsante viene premuto, la bocchetta si richiude e il sistema torna alla schermata iniziale. Nell'eventualità in cui le pillole dovessero strabordare, un messaggio di avvertenza verrà mostrato e le pillole in eccesso verranno scaricate dal fondo nel piattino di erogazione, così che lo stack non ecceda mai la capacità limite.
- ***Svuotamento***
>Dall'interfaccia, l'utente entra nella schermata dell'inventario. Per lo stack scelto, seleziona l'opzione "*Svuota*". A questo punto, lo stack d'interesse viene svuotato nel piatto terminale e il sistema azzera il numero di pillole.
- Questa operazione è richiesta dal sistema (bloccando il resto delle funzionalità fino a completamento) in caso delle pillole in uno stack siano scadute (è possibile specificare la scadenza delle pillole al momento della definizione dello stack).
- ***Modifica***
>Coincide con il primo riempimento. L'utente può richiedere di modificare le proprietà di uno stack (etichetta, colore, data di scadenza) e cambiare il tipo di pillole all'interno: ciò comporta una fase di svuotamento dello stack dalle pillole precedentemente inserite, seguita da una di riempimento.
- ***Erogazione***
> Quando l'orario corrente corrisponde a un evento di erogazione, il sistema, ammesso che non siano in corso eventi d'eccezione (es. pillole terminate, scadute o non prelevate), attiva il segnale acustico e mostra una notifica a schermo per segnalare l'evento. Da questo momento, il sistema attiva il sensore di prossimità e attende che l'utente si presenti di fronte l'erogatore per una manciata di secondi (al fine di evitare rilevamenti accidentali di entità diverse dall'utente), mostrando un timer che rappresenta il tempo rimanente per informare l'utente dell'attesa necessaria, poi eroga le pillole stabilite. Caterpill attenderà, mediante il sensore a infrarossi, che l'utente attraversi il varco terminale con la mano per segnalare al sistema che i medicinali sono stati prelevati e il piatto terminale è ora vuoto. L'assenza dell'utente per un periodo prolungato, il mancato prelievo della pillola in seguito all'erogazione, la scadenza delle pillole o un numero insufficiente di pillole da erogare comportano uno stallo del sistema, che segnalerà opportunamente sull'interfaccia la situazione d'errore e potrà riprendere il corretto funzionamento solo dopo che l'utente risolverà lo stallo presentandosi e gestendo il problema.

- Eventi d'eccezione
>Ci sono determinati casi in cui il sistema avvia una situazione di stallo in cui avverte l'utente e interrompe l'avanzamento del calendario di erogazione finché la causa dell'eccezione non viene gestita. 
Il sistema entra in stato di stallo:
>- In corrispondenza di un evento di erogazione, dopo aver atteso per un certo numero di minuti l'arrivo dell'utente
>- Dopo l'erogazione della pillola, se l'utente non la preleva per un certo periodo di tempo
>- Quando si verifica un evento di erogazione che comprende pillole scadute o terminate
>
>Ogni stallo termina quando l'utente si occupa di risolvere la problematica che l'ha causato (rimpinguando o cambiando le pillole, prendendo quelle erogate ecc...).
>
>In presenza di uno stallo, il sistema richiamerà l'attenzione dell'utente a intervalli regolari per un numero determinato di volte, sia con segnalazione acustica che visiva. Al termine dei richiami, solo l'avvertenza visibile sull'interfaccia rimarrà attiva.
>Durante il periodo di avvertenza e fino alla risoluzione dell'eccezione, tutti gli eventi del calendario che si verificano verranno aggiunti ad una coda, e verranno presentate in ordine all'utente al termine dello stallo, proponendo alternative per gestire gli eventi (saltarli, posticiparli, erogare).
##### Caratteristiche fisiche
