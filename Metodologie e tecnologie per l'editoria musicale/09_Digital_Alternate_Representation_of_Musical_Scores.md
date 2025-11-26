# DARMS (Digital Alternate Representation of Musical Scores)
Il **DARMS** è un formato alfanumerico nato negli anni '60 (manuale completo di Raymond Erickson, 1976).
A differenza del *Plaine & Easie Code* (che codifica il significato logico per l'incipit), il DARMS è stato concepito per la **tipografia musicale digitale**.
* **Approccio Tipografico:** Codifica i **simboli grafici** e la loro posizione spaziale, non direttamente il loro significato musicale.
* **Concetto di "Stato":** Per interpretare un simbolo (es. capire che nota è), il software deve conoscere il contesto globale (chiave, armatura, ecc.). Senza queste informazioni, il codice indica solo una posizione su una riga o uno spazio.
* **Sintassi Generale:** Blocchi di caratteri alfanumerici (solo maiuscole) separati da spazi.

---
## Codifica della Posizione (Space Codes)
Il DARMS non usa i nomi delle note (A, B, C...) ma la loro posizione fisica sul pentagramma tramite numeri interi detti **Space Codes**.
* **Sistema di numerazione:**
    * La **prima riga inferiore** corrisponde al numero **21**.
    * Le **linee** sono numeri dispari (21, 23, 25, 27, 29).
    * Gli **spazi** sono numeri pari (20, 22, 24, 26, 28).
    * I tagli addizionali seguono la stessa logica (sotto il 21 e sopra il 29).
### Scorciatoie (Shortcuts) per la posizione
Per risparmiare caratteri, il DARMS usa tecniche di soppressione:
1. **Two Suppression (Soppressione del 2):** Per i codici tra 20 e 29 (il pentagramma standard), si può omettere la decina "2".
    * *Esempio:* La linea 21 diventa `1`, lo spazio 22 diventa `2`.
    * *Eccezione:* Per distinguere i tagli addizionali inferiori (0-9) da queste abbreviazioni, ai tagli inferiori si premette uno zero (es. `01`, `02`).
2. **Sigma Suppression:** Se una nota ha la stessa posizione della precedente, il codice di posizione può essere omesso completamente.
## Valori Ritmici (Duration Codes)
Le durate sono indicate con lettere mnemoniche derivate dall'inglese. Il codice di durata segue il codice di posizione.
* **W** = Intero (*Whole*)
* **H** = Metà (*Half*)
* **Q** = Quarto (*Quarter*)
* **E** = Ottavo (*Eighth*)
* **S** = Sedicesimo (*Sixteenth*)
* **R** = Pausa (*Rest*) -> Si usa al posto della posizione.
**Sintassi:** `Posizione` + `Alterazione` + `Durata`
* *Esempio:* `5H` (Nota sulla terza linea, durata di metà).
* *Delta Suppression:* Se la durata è identica alla nota precedente, può essere omessa.
### Punti di valore e Alterazioni
* **Alterazioni:** Si scrivono tra la posizione e la durata. Simboli: `#` (diesis), `-` (bemolle), `*` (bequadro).
* **Punto di valore:** Si aggiunge un punto `.` dopo la durata.
    * *Attenzione:* La *Delta suppression* mantiene i punti precedenti. Per togliere un punto a una nota successiva, bisogna riscrivere esplicitamente il codice di durata senza punto.
## Elementi Grafici e Articolazioni
### Travature (Beams)
Non si usa un codice di durata esplicito per le note travate (viene inferito). Le travi sono definite da **parentesi tonde**:
* `(` apre la trave, `)` chiude la trave.
* Il numero di parentesi indica il numero di travi (es. `((` per semicrome).
### Legature di valore (Ties)
Si usa la lettera **J** dopo il codice di durata della nota di partenza.
* Per legature complesse, si può numerare la J (numeri dispari per l'inizio, pari per la fine).
### Gruppi Irregolari (Tuplets)
Richiedono due fasi:
1. **Definizione:** Si crea un pattern con sintassi `!n1dur1id:n2dur2` (es. "3 note da un ottavo nello spazio di 1 da un quarto") e gli si assegna un ID numerico.
2. **Utilizzo:** Si appende l'ID del gruppo alla durata delle note coinvolte.
## Accordi
Esistono tre metodi per scrivere accordi (note simultanee):
1. **Full Encoding:** Note separate da virgola `,`. Si ripetono tutti i dati per ogni nota.
2. **Space-pattern:** Celle separate da `|`. Le informazioni comuni (es. durata) si mettono alla fine.
3. **Base-increment:** Il più efficiente. Si scrive la nota base (bassa) + gli intervalli incrementali per le altre note.
    * *Esempio:* `1+2+2Q` (Nota base linea 1, poi sali di 2 posizioni, poi sali di altre 2, tutte di durata Quarto).
*Direzione dei gambi:* `U` (Up) e `D` (Down) possono forzare la direzione.
## Impostazione del Pentagramma (Metadati)
Questi codici iniziano solitamente con il carattere esclamativo `!`.
* **Chiavi:** `!G` (Sol/Violino), `!F` (Fa/Basso), `!C` (Do). Possono essere posizionate tramite *Space code*.
* **Armatura di chiave:** `!K` seguito dal numero e tipo di alterazioni.
    * *Esempio:* `!K2#` (Due diesis).
* **Metrica (Time Signature):** `!M` seguito dalla frazione.
    * *Esempio:* `!M3/4`.
* **Stanghette di battuta:** Rappresentazione grafica ASCII (`/`, `//`, `//:`, `://`).
## Decomposizione Lineare (Polifonia)
Per scrivere più voci sullo stesso pentagramma, si scrivono le voci in sequenza lineare, delimitate da codici speciali:
* Apertura: `!&`
* Separatore tra le voci: `&`
* Chiusura: `$&`
*Nota:* Spesso si usano i comandi `!U` e `!D` all'interno delle voci per forzare la direzione dei gambi e distinguere visivamente le parti.