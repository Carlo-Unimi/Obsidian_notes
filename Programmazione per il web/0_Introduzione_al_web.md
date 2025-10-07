# Introduzione al web
Servizio attraverso il quale si può accedere ad una risorsa remota presente su un calcolatore connesso ad internet. Il protocollo **World Wide Web** comprende la richiesta di una risorsa e la risposta da parte del calcolatore interpellato, strutturata con il linguaggio HTML: questa risorsa è del codice, che può contenere tramite allegato immagini, audio, video, etc.
### Evoluzione del web
**Web 1.0**: read-only
**Web 2.0**: read and write
**Web 3.0**: read-write and execute
# Introduzione a HTTP
In una rete i calcolatori che devono scambiarsi informazioni devono seguire dei **protocolli di rete**. Essi specificano i *formati dei dati*, la *struttura dei pacchetti* e la *velocità di trasmissione*. Questa "pila" di protocolli fa in modo che ogni pezzetto operi su una componente ben precisa, passando al pezzo successivo i dati richiesti e rielaborati.
## Struttura di internet
1) **Infrastruttura telematica**: regole che riguardano il livello fisico di internet (cavi, satelliti, etc..)
2) **Protocolli di trasmissione**: protocolli come TCP/IP assegnano ad ogni calcolatore un indirizzo univoco, in questo livello viene anche deciso l'instradamento dei messaggi tramite algoritmi appositi
3) **Protocollo applicativo**: protocolli che gestiscono richieste e risposte tra *client* e *server*.
4) **Contenuto delle applicazioni**: applicazioni come posta elettronica, World Wide Web, copia di files, etc.
### TCP/IP
> Schema di indirizzamento generale su sue livelli: **Indirizzo IP** e **Porta TCP**.

Devo conoscere l'indirizzo IP della macchina e la porta su cui trasmettere le informazioni.
#### Protocollo DNS
È il protocollo che associa un indirizzo logico (come www.larepubblica.it) ad un indirizzo IP.
### Paradigma client-server
L’utente usa il client per esprimere le sue richieste
Il client si collega al server e trasmette la richiesta
Il server risponde al client
Il client presenta la risposta all'utente
#### Il client
Si preoccupa di dialogare con l'utente, sfrutta tutte le possibilità fornite del calcolatore su cui viene eseguito e fornisce all'utente un'interfaccia intuitiva; tutto questo mentre elabora le richieste dell'utente e le risposte dei server.
#### Il server
Esso rende disponibili delle risorse, accetta richieste e risponde automaticamente (non bada alla provenienza della richiesta). È possibile organizzare un insieme di server in modo che siano collegati tra di loro.
In casi molto particolari, un server potrebbe essere eseguito dallo stesso calcolatore che esegue il processo client.
##### I servizi
Un server mette e disposizione dei servizi, o in generale delle **risorse**. Ciascun servizio è identificato da un numero di porta, su ciascuna porta è in ascolto il programma (*daemon*) che esegue le operazioni necessarie per l'espletazione del servizio, ognuno dei quali usa un proprio **protocollo**.
Ogni risorsa su internet è identificata da un nome univoco detto URL, composto da *protocollo di comunicazione*, *nome della macchina che possiede la risorsa* e *il nome della risorsa*.
### Il protocollo HTTP
> **HTTP** (Hypertext Transfer Protocol) è il “linguaggio” utilizzato per controllare l’invio di "pagine Web" via Internet.

Il protocollo HTTP prescrive le regole mediante le quali i browser effettuano le richieste e i server forniscono le relative risposte.
- **HTTP 1.0**: Su ogni connessione TCP viene inviato al più una singola risorsa e la connessione non è persistente
- **HTTP 1.1**: più risorse si possono inviare sulla stessa connessione TCP e la connessione è persistente
