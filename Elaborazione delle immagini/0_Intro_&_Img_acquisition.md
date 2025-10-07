> *Strictly speaking*, **Image processing** is the study of any **algorithm** that takes an image as input and returns an image as output.
> *Broadly speaking*, Image processing it also concerns with the **extraction of meaningful information** (attributes) from an images (Image Analysis).

##### From low-level to high-level:
1) ==Image Acquisition and Coding==: physical signal, digital conversion, coding, compression
2) ==Image Processing==: image enhancement, noise removal, restoration, feature detection, compression
	- **contrast adjustment**, typically by means of *point processing* 
	- **noise removal**, typically by means of *spatial filtering*
3) ==Image Analysis==: segmentation, image registration, matching
	-  **region detection/segmentation**, typically by means of *clustering*
	- **edge detection**, typically by means of *spatial filtering*
4) ==Computer vision==: object detection, recognition, shape analysis, tracking, use of artificial intelligence and machine learning
	- **classification, detection or segmentation**, typically by means of machine learning

# Luce e colore
Il **colore** è una serie di onde elettromagnetiche che l'*occhio umano  riesci a vedere*, diventando quindi una grandezza **psicofisica**.
> Il **colore** è l'interazione tra una o più fonti di luce, le proprietà di assorbenza/riflettanza di un determinato oggetto e il sistema visivo umano.

È evidente che il colore percepito di un oggetto dipende anche dalla composizione della luce che lo illumina, la quale altera le quantità delle onde elettromagnetiche riflesse.
## Fisica della luce e del colore
La luce si propaga come un'onda elettromagnetica la quale ha una determinata *frequenza* (che determina il colore percepito) e *ampiezza* (che determina l'intensità della luce).
#### Grandezze radiometriche
**Lunghezze d'onda**: $lambda=c/v$ in cui $c$ = velocità della luce e $v$ = frequenza.
**Energia radiante**: $E=hv=h/lambda$ in cui $h=6.626x10^-34$ Js (costante di Planck).
**Potenza radiante**: energia emessa, trasferita e ricevuta nell'unità di tempo.
**Radianza**: potenza radiante per unità infinitesimale di superficie irradiante.
**Irradianza (E)**: potenza radiante per unità infinitesimale di superficie irradiata (potenza ricevuta per unità di superficie irradiata).
### La luce
> La **luce** è la porzione di spettro elettromagnetico percepibile dal Sistema Visivo Umano. (da 430nm a 790nm)

Il passaggio della luce dall'aria ad un altro mezzo trasparente provoca la **rifrazione** cioè la deviazione dei raggi luminosi, con diversi indici di rifrazione a seconda della lunghezza d'onda (deviati in modo diverso). Lo ===spettro radiometro== divide la luce in input nelle diverse lunghezze d'onda e misura l'energia in ciascuna. Si riesce a misurare l'energia grazie ad un filtro sensibile alla singola lunghezza d'onda e a un rilevatore di energia dedicato.
## Percezione umana del colore
La luce colpisce la retine che contiene **fotorecettori**, i quali convertono le radiazioni in impulsi elettrici. La ===retina== contiene 2 tipi di fotorecettori: i **coni** e i **bastoncelli**; non hanno una distribuzione spaziale uniforme, ma è simmetrica rispetto alla fovea (punto di massima acutezza visiva).
![[Pasted image 20250930144838.png]]
#### I bastoncelli: visione scotopica
Sono distribuiti su tutta la retina, collegati tutti ad un terminale nervoso. Non hanno il compito di catturare i dettagli, ma bensì alla visione dell'intensità (grigi), codificando per un'immagine generale del campo visivo. Essi operano con bassa illuminazione.
#### I coni: visione fotopica
> I **coni** servono per la rilevazione di differenza cromatiche.

Esistono coni di 3 tipi: **long, medium e short** con frequenza 10:5:1 nella retina. Sono detti impropriamente ===R, G, B===. Sono all'incirca 6 milioni per occhio, posizionati intorno alla fovea; ognuno di essi è collegato al proprio terminale nervoso, essendo essi molto sensibili ai colori e ai dettagli fini.
### La percezione del colore
I coni e bastoncelli agiscono da **filtri spettrali**. Per ottenere l'uscita di un filtro $V_c$, lo spettro va pesato con la sensibilità di ogni cono: $\int E(lambda)R_C(lambda)\,$ $d(lambda)$. Ogni valore è scalare, quindi si ottiene un **tristimolo**.
Ovviamente non si può caratterizzare uno spettro con soli 3 numeri, infatti la maggior parte delle informazioni viene perduta; gli stimoli che riproducono lo stesso *colore* finale, vengono detti **metamerici**.
Il vantaggio dell'occhio è che bastano solo 3 colori primari per codificare un solo colore.
### La colorimetria
> Disciplina che ha per oggetto la **misura del colore**.

Si fonda su esperimenti di psicofisica, in particolare di *color matching*, che hanno l'obiettivo di capire se stimoli che appaiono uguali (metamerici) abbiano la stessa specifica numerica.
Un osservatore deve aggiustare i pesi (l'intensità) di luci primarie per corrispondere all'apparenza (tinta, saturazione e brillanza) di uno stimolo-test.
### Leggi di Grassman
![[Pasted image 20250930151158.png]]
## Rappresentazione del colore
> Uno **spazio colore** (o modello colore o sistema di colore) è uno strumento con il quale si può specificare, creare o visualizzare un colore; esso è necessario per definire un colore senza ambiguità.

Uno spazio colore è una specificazione di un sistema di coordinate e di un sotto-spazio al suo interno dove ogni colore è rappresentato da un singolo punto
### Spazio colore RGB
> Ogni colore è rappresentato dalle sue componenti spettrali di **rosso, verde e blu**.

Esso è basato su un sistema di coordinate cartesiane, dove il sotto-spazio di interesse è un cubo di spigolo unitario. Sui vertici sono disposti i colori primari, i secondari, il bianco (1, 1, 1) e il nero (0, 0, 0).
![[Pasted image 20250930151855.png]]
Il modello RGB si adatta perfettamente per dispositivi che usano la sintesi additiva per visualizzare le immagini, come i monitor.
### Spazio colore CMY
Come l'RGB, è basato su un sistema di coordinate cartesiane, dove il sotto-spazio di interesse è un cubo di spigolo unitario; esso adotta primari ideali per la **sintesi sottrattiva**: ciano, magenta e giallo.
C = 1-R
M = 1-G
Y = 1-B
### Spazio colore CMYK
vista la difficoltà di ottenere un nero di qualità con la sovrapposizione dei 3 pigmenti, si estende CMY a un modello quadricromatico CMYK che assume il nero (K) come quarto primario.
![[Pasted image 20250930152639.png]]
### Diagramma di cromaticità
Alcune volte interessa solo la direzione del vettore cromatico e non la potenza, quindi utilizziamo l'intersezione tra il vettore e il piano $X+Y+Z=1$.
![[Pasted image 20250930152837.png]]
Tutti i colori visibili sono rappresentabili da una terna compresa nel cono rappresentato nella prima figura; considerando il piano sopra citato, si ottiene il **diagramma di cromaticità CIE-xy**.
### Distanze negli spazi colore
Lo spazio CIE-xy è uno spazio colore **NON uniforme**, in quanto la distanza spaziale tra le coordinate non è un buon indicatore della distanza percettiva tra i colori.
*Ellissi: luogo dei colori appena distinguibili rispetto al colore del punto centrale*.
![[Pasted image 20250930153200.png]]
Gli spazi colore uniformi, ovvero che "appallottolano" queste ellissi, sono il **CIE Lu'v'** e **CIE Lab**. In quest ultimo le lettere L, a, b significano: *L=luminanza*, *a=varia tra verde e rosso*, *b=varia tra blu e giallo*.
![[Pasted image 20250930153410.png]]
### Modelli HSI e HLS
> Mezzo che permetta di descrivere i colori in un modo più vicino alla **naturale caratterizzazione dei colori da parte dell’uomo**.

- **Hue**: è un angolo che indica la tinta del colore (essendo rappresentato come un cono)
- **Saturation**: misura della purezza del colore
- **Value** (intensity): misura della luminosità del colore
![[Pasted image 20250930153736.png]]
## Formazione dell'immagine
I fattori che influenzano l'acquisizione di un'immagine sono:
- **proprietà della fonte di luce** (irradianza) -> caratterizzata dalle componenti *x,y,z* e la sua lunghezza d'onda *lambda*
- **proprietà della superficie** (riflettanza) -> ogni punto della scena ha la sua funzione di riflettanza particolare *r(x,y,z,lambda)*
- **luce riflessa** -> la luce che effettivamente arriva alla camera, combinata tramite moltiplicazione con luce irradiata e luce riflessa dalla scena *c(x,y,z,lambda)*
- **proiezione prospettica** -> la lente della camera fa mettere a fuoco il soggetto interessato, quindi fa sparire la "profondità" dell'immagine (la *z* si appiattisce). $c_p(x',y',lambda)=P(c(x,y,z,lambda))$
- **funzione di sensibilità per ogni sensore** -> per ogni camera, abbiamo 3 canali che caratterizzano un singolo pixel.
# Digitalizzazione dell'immagine
Come primo step, noi abbiamo un'immagine espressa in *dominio* e *codominio* espressi nel continuo ($R^2$). I computer non possono lavorare con informazioni nel continuo, quindi si ricorre alla **discretizzazione** con le tecniche del *sampling* e *quantizzazione*.
### Sampling spaziale
> Possiamo pensare il **sampling spaziale** come una moltiplicazione tra un segnale continuo e un *comb filter*.

Questo è un sampling su una sola dimensione, è applicabile su entrambe le dimensioni con un $comb(x',y')$: si ottiene l'immagine samplata con $f_c(x',y')*comb(x',y')$. Da qui otteniamo l'espressione che ci interessa $f(x'_i,y'_j)=f(i,j)$.
### Quantizzazione
> Discretizzazione dei valori di $f(i,J)$ in P livelli.

![[Pasted image 20251007144548.png]]
La quantizzazione regola il numero di tipologie di grigio in un'immagine, a partire da un "bianco e nero", fino alle più fluide transizioni tra colori.
### Rappresentare un'immagine
La struttura dati per rappresentare un'immagine è semplicemente un array 2D di valori. I valori in questione possono essere di ogni tipologia di dati in questi: bit, byte, int, float, double, etc..
### Pixel
> È il singolo valore in una griglia di campionamento di un'immagine.

Esso non corrisponde ad un punto, quanto più ad un'area che sia la più piccola possibile e trattabile allo stesso tempo.
#### Interpolazione 'Nearest-Neighbor'
> Associare ad ogni pixel in output, il valore del pixel più vicino ad esso nell'immagine di partenza.

Dato "n" il fattore di zoom, si deve calcolare qual è effettivamente il pixel più vicino a quello in output. Per fare ciò, divido le coordinate di arrivo per il fattore di zoom e arrotondo il risultato; facendo ciò posso trovare nell'immagine di partenza il pixel da cui prelevare le informazioni.
$O(x_o,y_o)=I(round(x_I),round(t_I))$
#### Interpolazione Bilineare
Applica 2 volte l'**interpolazione lineare**, prima sulle righe e poi sulle colonne. Essa considera i 4 pixel vicini a quello che poi verrà messo nell'immagine in output.
#### Interpolazione cubica
Vengono utilizzate delle interpolazioni cubiche, quindi i pixel coinvolti sono 16. È un metodo più pesante dal punto di vista computazionale, ma è molto più preciso di un'interpolazione lineare.
## Trasformazioni geometriche
> Le **trasformazioni geometriche** modificano lo spazio e le relazioni tra i pixel in un'immagine.

Si svolge in 2 step, ovvero la *trasformazione spaziale delle coordinate* e successivamente l'*assegnazione dei valori alla griglia precedentemente creata*.

*vedi slide M1_03_img_acquisition pag 44-56*
