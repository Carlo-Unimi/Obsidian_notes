# Protezione dei dati personali
Il Regolamento europeo 2016/679, noto come **GDPR** (*General Data Protection Regulation*), disciplina la protezione delle persone fisiche con riguardo al trattamento dei dati personali. Essendo un Regolamento, garantisce l’uniformità delle regole in tutti i paesi dell'Unione, superando le differenze territoriali. È importante precisare che la vecchia normativa italiana, il Codice della Privacy (D.Lgs. 196/03), non è stata cancellata ma resta in vigore. Essa coesiste con il GDPR per disciplinare aspetti specifici che la norma europea lascia agli Stati membri.
L'aspetto rivoluzionario del GDPR è il **principio di responsabilizzazione**. A differenza del passato, infatti, le norme non forniscono un elenco rigido di misure di sicurezza da applicare meccanicamente, ma impongono al titolare di valutare i rischi e adottare misure adeguate alla quantità e alla natura dei dati trattati. Il Regolamento ha inoltre risolto il problema dell'applicabilità territoriale: le norme valgono per tutte le società con sede nell’UE, ma anche per le società extra-UE che offrono beni o servizi a cittadini europei, prevedendo sanzioni amministrative molto ingenti in caso di illeciti per scoraggiare l'uso improprio dei dati.
L'oggetto della tutela è il **dato personale**, ossia qualsiasi informazione (testo, foto, video, audio, indirizzo IP) riguardante una persona fisica identificata o identificabile. Il GDPR non si applica, invece, ai dati raccolti per l’esercizio di attività a carattere esclusivamente personale o domestico. Viene definito trattamento qualsiasi operazione compiuta sui dati, come la raccolta, la registrazione, l’organizzazione, la strutturazione, la conservazione, la modifica, l’estrazione, la consultazione, l’uso, la comunicazione, il raffronto, la limitazione e la cancellazione.
## Tipologie di dati
Esiste un sottoinsieme di dati personali che richiede una tutela rafforzata, ovvero i **dati sensibili o particolari**. Questi includono le informazioni che rivelano l’origine razziale o etnica, le opinioni politiche, le convinzioni religiose, l’appartenenza sindacale, nonché i dati genetici, biometrici e quelli relativi alla salute, alla vita sessuale o all'orientamento sessuale. Bisogna inoltre fare una distinzione tecnica sulla riconoscibilità dell'utente:
- **Dati anonimi**: informazioni che non possono più essere ricondotte all'interessato in alcun modo; ad essi il GDPR non si applica.
- **Dati pseudonimi**: dati in cui l'identità è mascherata tramite codici per tutelare la riservatezza, ma poiché esiste una "chiave" (conservata separatamente) per risalire alla persona, questi restano dati personali e sono soggetti al GDPR.
## Gestione dei dati
La gestione dei dati deve seguire dei principi cardine per essere lecita:
- **Minimizzazione**: il trattamento deve limitarsi esclusivamente ai dati indispensabili e pertinenti rispetto alle finalità, senza eccedere nel numero o nella conservazione temporale.
- **Privacy by design e by default**: sono concetti fondamentali per la sicurezza. La Privacy by design impone che la protezione dei dati sia prevista fin dalla progettazione strutturale del sistema. La Privacy by default stabilisce che le impostazioni predefinite debbano essere orientate alla massima riservatezza: non deve esserci un consenso automatico o caselle pre-spuntate; deve essere l’utente a scegliere attivamente di condividere i propri dati o allargare le maglie della privacy.
## Informativa, consenso, e condizioni di liceità del trattamento
I due punti che vanno presi in considerazione nell'ambito dei dati sono **trattativa** e **consenso**.
Chiunque tratta dei dati lo può fare solo se esiste una **condizione di liceità** che giustifica quel trattamento. Basta che una di quelle condizioni, citate in una lista, si verifichi per giustificare il trattamento (*esempio: un contratto telefonico rientra in una condizione, quindi non serve che mi chiedano il consenso per trattare i miei dati al fine di farmi un nuovo contratto telefonico*). Un'altra situazione potrebbe essere il *trattamento medico*, oppure *pubblica amministrazione* e *perseguimento del legittimo interesse del titolare del trattamento o di terzi*.
### Consenso
> Il trattamento di dati diventa lecito (oltre alle casistiche sopra citate) se si da **il consenso**.

Qualsiasi **manifestazione di volontà libera, specifica, informata e inequivocabile dell'interessato**, con la quale lo stesso manifesta il proprio assenso, mediante dichiarazione o azione positiva inequivocabile, che i dati personali che lo riguardano siano oggetto di trattamento. Il consenso dato *a voce* è identico ad un consenso scritto, l'unica particolarità è che bisogna essere in grado **di dimostrarlo**; qualora il consenso venga revocato, esso deve cessare.
### Informativa
> L'**informativa** è la **motivazione del trattamento dei dati**, oltre ad una serie di informazioni riguardanti l'ente/persona che vuole trattare i miei dati (modalità, fini, etc..).

L'informativa, anche se non ricevo il consenso, deve comunque essere fornita al soggetto (o ai soggetti) di cui voglio raccogliere i dati.
## Information Security
Dei dati vanno protette tre componenti essenziali: **Availability**, **Confidentiality** e **Integrità**.
1) **Integrità**: garantire che i miei dati non vengano alterati
2) **Disponibilità**: dati facilmente disponibili all'occorrenza, per esempio con versioni ridondanti etc
3) **Privatezza**: garantire che i dati vengano trattati solo dalle persone autorizzate, specificate nell'informativa
Le misure di sicurezza per la protezione dei dati sono di tipo **fisico** e di tipo **logico**, ma nel campo dell'informatica è chiaramente maggiore la casistica logica. Alcuni esempi di misure di protezione:
- possedere una **procedura di autenticazione** come una password che protegga i dati all'interno di dispositivi
- **cifrare** dei dati o delle comunicazioni che avvengono tra più enti
- quando si **cancellano i dati** devono essere stati cancellati in modo sicuro (*non si possono buttare dei dischi con dati di terzi, ma è necessario disintegrarli o resettarli*)