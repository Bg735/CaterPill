### REQUISITI
|Requisito|Descrizione|Priorità|Business value|
|-|-|:-:|:-:|
|**Inserimento Pillole**|Il sistema permette all'utente di inserire fino a tre diversi tipi di pillole posizionati in stack indipendenti. L'utente deve inserire: etichetta ai singoli stack, data di scadenza relativa alle pillole e il numero di pillole da inserire . |H|MUST HAVE|
|**Svuotamento Pillole**| Il sistema permette all'utente di svuotare gli stack singolarmente.|H|MUST HAVE|
|**Modifica Pillole**| Il sistema permette all'utente di modificare le pillole inserite per ogni stack. Il sistema svuota lo stack precedente e richiede il riempimento con le nuove pillole.|H|MUST HAVE|
|**Calenedario Erogazione**|Il sistema permetta all'utente di decidere quanti e in quali giorni deve erogare la pillola. |H|MUST HAVE|
|**Erogazione Pillola**|Quando l'orario corrente è essattamnete uguale all'orario prestabilito il sistema fa suonare un buzzer e invia una notifica all'utente. Il sistema inoltre attiva un sensore di prossimità in attesa che l'utente si avvicini per prelevare la pillola. L'utente deve attendere circa due secondi prima che il sistema eroghi la pillola.|H|MUST HAVE|
|**Svuotamento Pillole Scadute**|Il sistema richiede lo svuotamento degli stack che contengono pillole scadute. L'erogazione delle  |H|MUST HAVE|
|**EROGAZIONE-ASSSENZA UTENTE**|Il sistema non eroga la pillola e lo notifica all'utente. Il sistema va in stato di stallo dopo che per tre volte (cinque minuti di distanza per volta) l'utente non si è presentato o ha posticipato l'erogazione della pillola(max 3).| H |MUST HAVE|
|**EROGAZIONE-MANCATO PRELIEVO DELLA PILLOLA**||||
|**EROGAZIONE-NUMERO INSUFFICIENTE DI PILLOLE NELLO STACK**|L'insufficienza si verifica quando il sistema deve erogare un numero di pillole maggiore (>) rispetto a quello che è presente nello stack. Altrimenti il sistema va in stallo.| H| MUST HAVE|
|**EROGAZIONE-PILLOLE SCADUTE**|DA DECIDERE|||
|**ERRORE-STALLO**|Se il sistema si trova in stato di stallo quando si presentano i casi di erroe riguardanti Riempimento ed Erogazione. A questo punto viene attivata una lista e all'utente vengono presentate in ordine all'utente al termine dello stallo0 porponendo alternative per egstirle.Il termine dello stando si verifica quando  l'evento scatenante dello stallo viene gestito dall'utente. |H |MUST HAVE
|**RIEMPIMENTO-SATURAZIONE STACK**|Durante la modalità di riempimento il sistema avverte l'utente che il tubo ha raggiunto la quantità indicativa di riempimento (es. 10 pillole inserite), l'utente ne può inserire anche altre. Il sistema rileva la saturazione del tubo e automaticamente svuota una parte del tubo (es. 3 pillole). L'utente è invitato a inserie altre pillole|H|MUST HAVE|
|GUI| Interfaccia|H|MUST HAVE|
