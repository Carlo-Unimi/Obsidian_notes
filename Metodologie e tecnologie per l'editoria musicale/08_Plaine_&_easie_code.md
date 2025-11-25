# Plaine & Easie Code

## Introduzione e Finalità
Il **Plaine & Easie Code** è un formato di rappresentazione alfanumerica della musica. Nasce con l'idea di utilizzare i caratteri ASCII (*quelli presenti sulle macchine da scrivere o tastiere standard*) per creare equivalenti informativi delle partiture.
* **Natura dello standard:** È uno standard bibliotecario mantenuto dalla IAML (*International Association of Music Libraries*) e dal RISM (*Répertoire International des Sources Musicales*).
* **Scopo principale:** Non serve a codificare intere opere, ma a rappresentare **incipit musicali** (le prime battute di un brano) per facilitare l'identificazione e il confronto delle fonti, specialmente nei cataloghi digitali.
* **Vantaggi:** Compattezza, interoperabilità, formato aperto (no royalties).
* **Svantaggi:** Difficile leggibilità umana (distanza dall'aspetto grafico), limiti nella polifonia complessa.
## Integrazione nei Cataloghi (MARC)
Il codice è integrato nei formati standard per la catalogazione bibliografica:
* **UNIMARC:** Campo **036** ($m, $n, $o, $p).
* **MARC21:** Campo **031** ($g, $n, $o, $p).
**Cosa codificare nell'incipit?**
Di norma si codifica la parte più acuta (es. violino o voce soprano) per un'estensione minima di **3 battute** o **10 note** non ripetute, omettendo dinamiche e segni espressivi.

---
## Struttura del Codice: I Metadati (Header)
Prima della notazione vera e propria, è necessario definire l'impianto del pentagramma. Ogni elemento è identificato da un prefisso speciale.
### Chiave (Prefisso `%`)
Sintassi: `%` + [Forma] + [Notazione] + [Posizione]
* **Forma:** G (Violino), F (Basso), C (Do).
* **Notazione:** `-` (moderna), `+` (mensurale).
* **Posizione:** Numero da 1 (riga inferiore) a 5 (riga superiore).
*Esempio:* `%G-2` (Chiave di Violino in notazione moderna sulla seconda riga).
### Armatura di Chiave (Prefisso `$`)
Sintassi: `$` + [Alterazione] + [Note alterate]
* **Alterazione:** `x` (diesis), `b` (bemolle).
* **Note:** Lettere maiuscole delle note alterate.
*Esempio:* `$xFC` (Fa diesis e Do diesis -> Re Maggiore / Si minore).
### Indicazione Metrica (Prefisso `@`)
Sintassi: `@` + [Frazione o Simbolo]
* **Frazione:** `@3/4`, `@12/8`.
* **Simboli:** `@c` (4/4 o tempo ordinario), `@c/` (tempo tagliato).
* **Mensurale:** `@o` (Tempus perfectum).

---
## La Notazione Musicale (Il corpo del codice)
Dopo i metadati, separata da uno spazio, inizia la notazione.
La definizione completa di una nota segue logicamente questo ordine (anche se può variare per le regole di stato):
> **Ottava + Valore Ritmico + (Alterazione) + Altezza**
### Concetto di "Stato" (Fondamentale)
Il formato è ottimizzato per la brevità. **L'ottava e la durata sono "stati" che persistono:** una volta specificati per una nota, valgono per tutte le note successive finché non vengono esplicitamente cambiati.
*Default (non documentati):* Ottava centrale e durata di un quarto.
### Sintassi degli elementi
1. **Altezza:** Lettere maiuscole anglosassoni (**A**-**G**).
2. **Ottava:**
    * `'` (apice): Ottava centrale. Si aggiungono apici per salire (`''`, `'''`).
    * `,` (virgola): Ottava sotto la centrale. Si aggiungono virgole per scendere (`,,`).
3. **Valori Ritmici (Numerici):**
    * **1** = Intero (Semibreve)
    * **2** = Metà (Minima)
    * **4** = Quarto (Semiminima)
    * **8** = Ottavo (Croma)
    * **6** = Sedicesimo (Semicroma) *[Attenzione: non è 16]*
    * **3** = Trentaduesimo (Biscroma) *[Attenzione: non è 32]*
    * **Punto di valore:** Si aggiunge un punto al numero (es. `4.`).
4. **Alterazioni (Tipografiche):**
    * Vanno inserite **prima** dell'altezza, solo se presenti graficamente in partitura (non logiche).
    * `x` (diesis), `b` (bemolle), `n` (bequadro).
5.  **Pause:**
    * Si usa il trattino `-` al posto del nome della nota (es. `4-` è una pausa di semiminima).
    * Pause multibattuta: `=` seguito dal numero di battute (es. `=24`).

---
## Elementi Strutturali e Articolazioni

* **Stanghette di battuta:** `/` (semplice), `//` (doppia), `//:` e `://` (ritornelli). Non richiedono spazi.
* **Accordi:** Le note simultanee sono separate da `^` (es. `2C^E^G`).
* **Travature (Beaming):** Indicate da parentesi graffe `{ }` che racchiudono le note unite dalla trave. (es. `{8CDE}`).
* **Legature di valore (Tie):** Simbolo `+` dopo la nota legata.
* **Corona:** Note racchiuse tra parentesi tonde `( )`.
### Gruppi Irregolari (Tuplets)
Sintassi: `durata` `(` `note` `;` `numero` `)`
* La parentesi aperta è preceduta dalla durata complessiva del gruppo.
* La parentesi chiusa è preceduta da `;` e dal numero di note nel gruppo.
*Esempio terzina:* `4(8CDE;3)` (Terzina di crome che occupa lo spazio di un quarto).
### Abbellimenti
* **Trillo:** `t` posto **dopo** la nota.
* **Acciaccature/Appoggiature:** `g` o `q` seguiti dall'altezza, posti **prima** della nota principale.

---
## Scorciatoie (Shortcuts)
Per rendere il codice più compatto, esistono sintassi abbreviate:
1. **Terzine:** Si possono omettere durata e numero se standard (es. `(CDE)` invece della sintassi completa).
2. **Ripetizione Melodico-Ritmica:**
    * Si delimita il blocco da ripetere con `!`.
    * Si usa `f` per ogni ripetizione successiva.
    * *Esempio:* `!6{GxFEF}!fff` (definisce il pattern e lo ripete 3 volte).
3. **Ripetizione di Battuta:**
    * Il carattere `i` racchiuso tra stanghette `/i/` ripete la battuta precedente.
4. **Schemi Ritmici:**
    * Scrivendo una sequenza di numeri prima delle note, si imposta un pattern ritmico ciclico che si applica alle note seguenti (es. `8.6` applicato a una scala renderà la scala ritmicamente puntata).
## 7. Strumenti
* **Verovio PAE Editor:** Strumento online per visualizzare e comporre codice Plaine & Easie, utile per verificare la correttezza della sintassi.