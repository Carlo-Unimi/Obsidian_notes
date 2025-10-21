# OMR
> La locuzione **optical music recognition (OMR)** si traduce letteralmente come riconoscimento ottico della musica.

Si tratta di un campo di ricerca che indaga su come leggere e interpretare attraverso un computer la notazione musicale presente nei documenti «tradizionali». L'**obiettivo** delle tecniche di OMR è permettere a un sistema automatico di produrre una versione di uno spartito o partitura musicale, scritta a mano o stampata, interpretabile da parte di un elaboratore (machine-readable). Le tecniche OMR permettono il **passaggio dal dominio analogico a quello digitale**.
### Storia e tappe fondamentali
I primi esperimenti con musica a stampa si attuano alla fine degli **anni ‘60** presso il Massachusetts Institute of Technology (MIT), grazie all'avvento degli scanner per immagini. Tra il **1980 e il 1984**, un gruppo di ricerca giapponese dell'Università di Waseda sviluppa un robot umanoide specializzato, chiamato WABOT-2 (WAseda roBOT), in grado di leggere lo spartito di fronte a esso e di accompagnare un interprete all'organo digitale. Vennero sviluppati successivi programmi chiamati **MIDISCAN** e **SmartScore**.
## OCR e OMR
> L’**optical character recognition (OCR)** è il riconoscimento ottico dei caratteri che ha luogo su testi tradizionali.

Differenza tra OCR e OMR: 
- la notazione musicale è un sistema di scrittura il cui alfabeto è costituito da primitive ben definite (gambi, teste delle note), ma è la loro configurazione, ossia come sono disposte sul rigo, che ne determina la semantica. **I simboli sono spesso sovrapposti, non sono agevolmente scontornabili come le lettere** (che hanno intorno dello spazio bianco), quindi risultano implicitamente più complessi da enucleare e da riconoscere.
- un sistema OCR mira al riconoscimento di lettere e parole, e con qualche eccezione (vocaboli appartenenti a un dizionario sconosciuto, sigle e acronici), **solo alcune combinazioni di lettere hanno un senso. Per analogia, un sistema OMR dovrebbe verificare anche la plausibilità semantica della musica** (ad es., Mozart non avrebbe mai scritto un accordo con Do, Do# e Re simultaneamente presenti).
- Sebbene esistano sistemi di scrittura con set di caratteri molto complessi (si pensi al cinese), lo **scenario musicale implica una gamma molto ampia di simboli**. Per i simboli musicali c’è grande **variabilità anche sulle dimensioni**: si va da elementi minuscoli come un punto di valore o un segno di articolazione a elementi che potenzialmente si estendono su un’intera pagina come una parentesi graffa.
- al netto dei necessari ritorni a capo, il **testo può essere visto come un flusso unidimensionale di informazioni, mentre la notazione musicale implica relazioni spaziali bidimensionali**. In un’ipotetica visualizzazione in stile *scroll view*, sull'asse orizzontale si trova il tempo e sull'asse verticale le diverse voci che operano in parallelo. Per analogia, è come se un testo letterario fosse costituito da più righe che procedono in parallelo.
### Utilità OMR
Studenti di musica, musicisti e compositori possono impiegare un sistema OMR per **importare nel computer la propria notazione manoscritta e facilitare il processo di composizione**, trascrizione, modifica e conservazione della musica. Nell'archivio di un’istituzione musicale, l'OMR può agevolare operazioni a partire dalla **copia analogica quali l’estrazione delle parti orchestrali**, il cambio di organico o tonalità d’impianto, ecc. In una biblioteca o in altro contesto professionale, un sistema OMR può agevolare la **ricerca all'interno di spartiti e partiture**, supportando studi musicologici quantitativi su larga scala.
### Approcci e tecniche
Il processo di riconoscimento della notazione musicale è in genere suddiviso in passaggi più piccoli gestiti con **algoritmi di pattern recognition**. La maggior parte di essi condivide un’**architettura a pipeline**: ogni fase esegue una determinata operazione prima che si passi alla fase successiva. Un problema comune dell’approccio a pipeline è che gli **errori e gli artefatti propri di una fase precedente si propagano**. Partendo da una scansione perfetta della musica, il riconoscimento può essere risolto con una sequenza di passi algoritmici relativamente semplici. Tuttavia, *il processo diventa notevolmente più difficile per scansioni scadenti o musica manoscritta, che molti sistemi non riescono a riconoscere del tutto*.
Anche se tutti i simboli venissero rilevati perfettamente, è comunque **difficile recuperare la semantica musicale a causa di ambiguità** e non infrequenti **violazioni delle regole di notazione musicale**.
![[Pasted image 20251021101414.png]]
![[Pasted image 20251021101447.png]]
### Approcci recenti e output attesi
Con l’avvento del **deep learning**, l'approccio a molti problemi di artificial vision è passato dalla programmazione imperativa e dalle euristiche manuali all'apprendimento automatico. Nel riconoscimento ottico della musica, il deep learning è stato applicato con successo alle fasi di *elaborazione del rigo, di rilevamento degli oggetti musicali e di ricostruzione della notazione musicale*.
# Leggii musicali elettronici
Negli ultimi tempi si sta assistendo a una rivoluzione nel campo dell’editoria musicale che riguarda la fruizione di un’edizione musicale: non più attraverso la stampa tradizionale, ma tramite dispositivi elettronici che permettano di leggere e di interagire con la partitura in formato digitale.
Da anni si sta anche promuovendo l’**utilizzo di leggii musicali elettronici (digital music stand)**. Fino a poco tempo fa il loro successo era limitato, per via dei limiti tecnici, dei costi, della difficile reperibilità, della scarsa conoscenza di tali dispositivi e di una certa resistenza da parte dei musicisti.

*Riguardarsi concetti di: PPI (Pixel Per Inch), Aspect Ratio, Risoluzione, Visualizzazione verticale/landscape.*
### Vantaggi rispetto all'editoria tradizionale
- Avere sempre con sé una **sterminata biblioteca musicale**, trasportando un peso e occupando dimensioni molto contenute.
- **Scaricare dalla rete partiture** musicali e poterle leggere subito, oppure fotografare o scansionare da tablet le partiture.
- **Annotare fraseggi**, diteggiature, dinamiche, diteggiature, ecc. e salvare la stessa partitura in differenti versioni.
- Utilizzare dispositivi wireless per le **voltate di pagina, rendendo autonomi i musicisti**.
- **Organizzare e cercare le partiture in un archivio**, ad esempio per autore, per strumento, per titolo, per parola chiave, … 
- **Creare diverse successioni di brani prestabilite**, utili in caso di concerti o altre esecuzioni.
- **Associare alla partitura una registrazione**.
### Funzionalità richieste dalle app
**Eliminare il bordo intorno alle pagine** è fondamentale per sfruttare al massimo le ridotte dimensioni dello schermo dei tablet. 
In alcuni casi, la dimensione del carattere musicale viene quasi raddoppiata eliminando il bordo.
Poter **inserire agevolmente annotazioni** (fraseggi, diteggiature, commenti, alterazioni di cortesia, ecc.) e di poter salvare diverse versioni annotate.
Possibilità di utilizzare un **dispositivo wireless per la voltata di pagina** (*chiamato AirTurn*). Azione da sempre una problematica per i musicisti, in questo contesto viene raddoppiata per via della visualizzazione di una sola pagina alla volta rispetto alla doppia pagina di un volume tradizionale. Alcune applicazioni hanno cercato di introdurre controlli alternativi per la **voltata di pagina**:
- utilizzo di un metronomo;
- scrolling continuo della partitura;
- utilizzo del microfono (con un soffio) oppure della videocamera (passaggio della mano o movimento della testa);
- collegando uno smartphone via wireless, con passaggio del piede sopra la videocamera del cellulare appoggiato a terra;
- con una registrazione audio nella quale vengono indicate e memorizzate le voltate. In seguito, l’applicazione è in grado di riconoscere l’esecuzione, anche se eseguita con tempi diversi.
Chiaramente tutte queste *operazioni devono essere svolte in modo veloce, anche se il file maneggiato è di grandi dimensioni*.