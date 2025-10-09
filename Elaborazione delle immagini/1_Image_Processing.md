# Processamento delle immagini
## Istogrammi per rappresentare immagini
Un istogramma rappresenta il tot numero di pixel che codificano per un certo colore presente nell'immagine. Una delle prime osservazioni che possiamo trarre è che se in un istogramma ci sono dei pixel con valore 255, solitamente si dice che l'immagine è bruciata. È molto difficile avere dei colori puri in un'immagine scattata, senza che essa sia sovra-esposta. Ovviamente si possono creare degli istogrammi per tutti e tre i *layer* di un'immagine RGB.
Con gli istogrammi si perdono le correlazioni spaziali sull'immagine e quelle anche relative ai canali dell'immagine (un pixel, avendo 3 valori, può andare a scomporsi in punti diversi dei 3 istogrammi disegnati).
Se analizziamo anche il canale della **luminanza**, **nessun canale RGB codifica precisamente per essa**.
Spesso gli istogrammi si esprimono in termini di probabilità, quindi è standard la pratica di normalizzare l'istogramma su cui si lavora: questo processo di svolge dividendo per *N* il numero di pixel che codificano per un certo valore. La di tutti i contributi per ogni *k*, il risultato è sicuramente 1.
### Distribuzione cumulativa
Ci indica per ogni valore *k* qual è la probabilità di avere un pixel con un valore <= *k*. Sarà una funzione monotona crescente, non può mai decrescere (ma può rimanere uguale).
Un'osservazione molto indicativa è lo *slope* della curva cumulativa, che più è lineare, più sarebbe ottimale. Se la salita della curva inizia dopo rispetto allo 0 o finisce prima, vuol dire che alcuni pixel sono omissibili.
## Point processing
> Data un'immagine **I**, l'operatore **T** è quell'operazione che viene applicata ad ogni valore che codifica i pixel nell'immagine, dando un'ulteriore immagine **O(x,y)** in uscita.

$O(x,y)=T[I(x,y)]$
Il filtro **T**, nel *point processing*, viene applicato ai soli valori che dobbiamo trasformare. Nessun vicino viene preso come valore per calcolare l'output, quindi non mi interessa neanche la dimensione dell'immagine. Analiticamente possiamo descriverla come:
$$
r=T(s); s,r∈[0,255]
$$
Esempio: $r=3*s+20$
Le trasformazioni che posso adoperare sono la traslazione verso l'alto/basso (con + o - 20) e aumentare/diminuire la pendenza della trasformazione (che può essere rappresentata graficamente come una retta).
Dato che in un'immagine ho 3 layer, li processo **con una sola funzione di Point Processing**, non con 3 diverse, altrimenti verrebbero dei risultati non naturali.
### Gamma correction
Le trasformazioni non sono per forza lineari, ma si possono usare anche delle **Gamma correction** che, tramite un indice *gamma*, modificano la linea di correzione rendendola curva (sopra o sotto la bisettrice del quadrante).
![[Pasted image 20251009115842.png]]
#### Gli effetti sull'istogramma della Gamma correction
L'osservazione che possiamo fare sugli istogrammi è che (nel caso della correzione positiva) la pancia dell'istogramma si è spostata più avanti, perchè sto effettivamente aumentando la brightness dell'immagine. Gli spike che si vedono nell'istogramma sono degli errori nell'arrotondamento, dato che dobbiamo campionare dei valori nel reale.
### Equalizzazione degli istogrammi
L'equalizzazione di un istogramma è mirata alla *brightness enhancement*. L'operazione che svolge questa equalizzazione è la funzione di distribuzione cumulativa, normalizzata:
$$
s=T(r)=255⋅P_r(r)
$$
Quindi con la *cdf* normalizzata, riusciamo a contrastare un'immagine che occupa un piccolo range dinamico dei valori. È l'immagine stessa che ci dice di quanto contrasto ha bisogno, in modo da sfruttare tutto il range dinamico.
*Un'immagine già ben contrastata, avrà una cdf praticamente lineare.*
![[Pasted image 20251009123211.png]]
