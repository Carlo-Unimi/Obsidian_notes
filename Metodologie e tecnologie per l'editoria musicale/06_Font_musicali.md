# Caratteri e font musicali
In editoria, la scelta del carattere è fondamentale per la leggibilità e l'estetica di un testo. Questo principio si applica anche alla musica, dove la notazione deve essere chiara, precisa e coerente.
## Caratteri e font tradizionali
Prima di analizzare i font specifici per la musica, è necessario comprendere la **terminologia di base della tipografia digitale**.
### Caratteri, glifi e font
Alla base della materia grafica troviamo i caratteri, che vengono organizzati in insiemi coerenti per formare caratteri tipografici.
> I **caratteri** sono i mattoni costitutivi della materia grafica. Un insieme di caratteri studiati secondo gli stessi principi formali costituisce un **carattere tipografico** (in inglese *typeface*). Il file digitale che permette di utilizzare tale carattere è chiamato **font**.

Ogni carattere può avere diverse rappresentazioni grafiche.
> Il **glifo** (*glyph*) è la rappresentazione grafica specifica di un carattere. Ad esempio, A, a, **a** e *a* sono glifi diversi dello stesso carattere all'interno del medesimo carattere tipografico.

*L'uso comune della parola "font" al posto di "carattere tipografico" è un errore tipico dell'era digitale, simile a confondere un file MP3 con il brano musicale che contiene.*
### Principali categorie di caratteri
I caratteri tipografici si dividono in due macro-categorie principali, basate sulla **presenza o assenza di elementi decorativi** alle estremità delle lettere.
#### Serif
> **Serif** è un termine francese che significa **grazia**. I caratteri serif presentano degli allungamenti, solitamente ortogonali, posti alle estremità di un carattere.

Questi elementi sono nati con il **carattere lapidario romano**, dove erano funzionali a una più semplice incisione della pietra. Oggi vengono utilizzati per rendere il carattere più elegante e aggraziato, e sono molto diffusi nella stampa di libri in quanto facilitano la lettura su carta.
#### Altre categorie
Oltre a **serif** e **sans-serif** (senza grazie), esistono altre categorie di caratteri, tra cui:
-   **Gotici** (*blackletter*): Caratteri complessi e spigolosi, come quelli usati da Gutenberg per la prima stampa della Bibbia.
-   **Script**: Caratteri che simulano la calligrafia e la scrittura a mano.
-   **Fantasy**: Caratteri decorativi che evocano stili particolari.
### Varianti di un carattere
Un carattere tipografico può includere numerose varianti, che vengono spesso distribuite come file font separati. Le principali varianti sono:
-   **Normali** (*roman* o *regular*): La versione standard del carattere.
-   **Peso**: Lo spessore del carattere, che varia da versioni sottili (*light*, *thin*) a molto spesse (*bold*, *black*, *ultra*).
-   **Obliquo** (*oblique*): Una versione inclinata del font normale, senza modifiche estetiche.
-   **Corsivo** (*italic*): Un font progettato con scelte grafiche ed estetiche diverse, non una semplice inclinazione del carattere *regular*.
-   **Compresse e allargate** (*condensed* ed *extended*): Varianti in cui i glifi sono disegnati per essere più stretti o più larghi del normale, senza ricorrere a uno stiramento (*stretching*) artificiale.
### Tipi di caratteri: vettoriali e matriciali
I font digitali possono essere descritti in due modi principali.
> In un **carattere vettoriale**, i glifi sono definiti da istruzioni matematiche (una giustapposizione di linee rette e archi) che ne disegnano i contorni.

L'approccio opposto è quello dei **caratteri matriciali** (*bitmap*), dove ogni glifo è rappresentato da una griglia di punti (pixel).
#### Vantaggi dei caratteri vettoriali
-   **Scalabilità**: Possono essere ridimensionati a qualsiasi dimensione senza perdita di qualità, a differenza dei caratteri bitmap che sgranano se ingranditi.
-   **Efficienza**: Un unico modello matematico può generare tutte le varianti di stile (grassetto, corsivo), occupando in definitiva meno spazio di memoria rispetto a dover salvare un bitmap per ogni stile e dimensione.
-   **Flessibilità**: Permettono trasformazioni complesse con risultati esteticamente superiori.
### Formati dei font
I formati più comuni per i caratteri vettoriali sono:
-   **TrueType Fonts (TTF)**: Formato standard sviluppato da Apple e Microsoft alla fine degli anni '80.
-   **OpenType Fonts (OTF)**: Basato su TrueType, è oggi ampiamente utilizzato su tutte le piattaforme.
-   **Web Open Font Format (WOFF/WOFF2)**: Formato ottimizzato con compressione per l'uso sul web, per ridurre i tempi di caricamento delle pagine.
-   **SVG Fonts/Shapes**: I glifi sono disegnati in formato *Scalable Vector Graphics* (SVG).
-   **Embedded OpenType Fonts (EOT)**: Versione compatta di OpenType per essere incorporata (*embedded*) nelle pagine web.

Per utilizzare un font specifico su una pagina web, si ricorre alla regola CSS `@font-face`, che permette di specificare il nome della famiglia di font e il percorso del file da caricare.

```css
@font-face {
  font-family: myFirstFont;
  src: url(sansation_light.woff);
}

div {
  font-family: myFirstFont;
}
```
## Font musicali
L'applicazione dei principi della tipografia alla notazione musicale ha portato alla creazione di font specializzati, progettati per rappresentare in modo chiaro e coerente il vasto repertorio di simboli musicali.
### Il primo font musicale: Sonata
Sebbene i primi software di notazione risalgano agli anni '60, il primo vero e proprio font dedicato alla musica è stato **Sonata**, progettato nel 1985 da Cleo Huggins per Adobe.
L'idea alla base di Sonata era quella di mappare i simboli musicali sui tasti di una tastiera QWERTY standard, utilizzando **associazioni mnemoniche** basate sulla somiglianza delle forme. Ad esempio:
-   La **chiave di sol** era mappata sul tasto `&`.
-   L'alterazione **diesis** era mappata sul tasto `#`.
Questo approccio, sebbene limitato (Sonata includeva meno di 200 glifi), ha gettato le basi per i futuri font musicali, come **Petrucci** (usato da Finale) e **Opus** (usato da Sibelius), che ne hanno seguito il layout iniziale, espandendone notevolmente il numero di glifi.
### Unicode e la musica
Per standardizzare la rappresentazione dei caratteri in tutte le lingue e sistemi di scrittura, è stato creato lo standard **Unicode**.
> I **code points** sono valori numerici univoci che vengono mappati su caratteri specifici. Un **plane** è un gruppo contiguo di 65.536 (2¹⁶) *code points*.

Lo standard Unicode è stato arricchito per includere anche un repertorio di simboli musicali, collocati nell'intervallo da `U+01D100` a `U+01D1FF`. Questo insieme iniziale include simboli per la notazione moderna, mensurale e gregoriana.
## L'iniziativa SMuFL
Il set di caratteri musicali previsto da Unicode si è rivelato insufficiente per le esigenze della notazione musicale convenzionale. Per questo motivo è nata l'iniziativa SMuFL.
> **SMuFL** è l'acronimo di **Standard Music Font Layout**. È una specifica che fornisce un metodo standard per mappare migliaia di simboli musicali all'interno di un'area di codici Unicode non allocata.

L'obiettivo di SMuFL è creare una **mappatura standard** per i glifi musicali, adottata sia dai produttori di software che dai *font designer*, a beneficio di tutta la comunità.
### SMuFL e Unicode
SMuFL sfrutta le **Private Use Area (PUA)**, ovvero intervalli di codici che, per definizione, non vengono assegnati dallo standard Unicode e sono quindi liberi per usi specifici. In particolare, SMuFL utilizza la PUA del **Basic Multilingual Plane (BMP)**, il piano 0 di Unicode, a partire dal *code point* `U+E000`.
Lo standard SMuFL attuale comprende:
-   Poco meno di 2500 caratteri **consigliati**.
-   Alcune centinaia di glifi **opzionali ma consigliati**, che includono legature e varianti alternative di altri simboli.
È importante notare due aspetti:
1.  I font **non sono tenuti a supportare tutti i glifi** previsti dai *code points* Unicode.
2.  La PUA utilizzata da SMuFL potrebbe essere impiegata per altri scopi, rendendo l'interpretazione dei codici ambigua in contesti diversi.
Di conseguenza, quasi nessun font non dedicato alla musica supporta i *code points* di SMuFL. La specifica SMuFL è pubblicata dal **W3C Music Notation Community Group**, ma non è uno standard W3C ufficiale.
### Il font Bravura
> Il font di riferimento per l'iniziativa SMuFL è **Bravura**, sviluppato da *Steinberg* per l'editor di partiture digitali Dorico.

Bravura è rilasciato con una licenza libera e *open source* (**SIL Open Font License**), che ne permette l'utilizzo, la modifica e la distribuzione gratuita.
#### Altri font SMuFL
Oltre a Bravura, esistono numerosi altri font che implementano la specifica SMuFL, tra cui:
-   **November 2.0**: Il primo font commerciale a supportare SMuFL.
-   **Petaluma**: Un font che richiama lo stile delle trascrizioni manuali del *Real Book*.
-   **Leland**: Il font di default del software MuseScore (dalla versione 3.6).
-   **Sebastian**: Un font che mette a disposizione anche il codice sorgente.
-   **Verovio**: Il font di default per il formato Music Encoding Initiative (MEI).
### Supporto software
La specifica SMuFL è supportata da un numero crescente di applicazioni musicali.
Tra i principali **digital score editors** che la utilizzano ci sono:
-   **Dorico** di Steinberg
-   **Finale** di MakeMusic (dalla v. 27)
-   **MuseScore** (dalla v. 2.0)
-   **Capella** (dalla v. 8)
Inoltre, altri software si basano su SMuFL per la visualizzazione della notazione, come la *digital audio workstation* **Logic Pro X** di Apple e il software open source **Verovio**.