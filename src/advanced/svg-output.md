% Uscita SVG

Slic3r può produrre un output destinato ad altri tipi di stampanti 3D che richiedono
che ogni layer sia rappresentato come immagine, ad esempio le stampanti DLP a resina
o a letto di polvere. Queste stampanti si aspettano un'immagine solitamente composta
da una silhouette bianca su sfondo nero (vedi fig.). Quasi tutti i formati immagine
possono essere utilizzati (bmp, png, ecc.), tuttavia, poiché l'immagine potrebbe dover
essere ridimensionata, in genere è preferibile usare un formato vettoriale anziché un
formato bitmap. Per questo motivo, è comune utilizzare il formato Scalable Vector 
Graphics (SVG).

![Esempio di slice
SVG.](images/svg_output/example_svg_slice.png "fig:")

Slic3r offre la possibilità di generare un output SVG adatto a tali stampanti. 
Invece di utilizzare il `Plater`, il processo inizia selezionando l'opzione 
`Slice to SVG...` dal menu `File`. Verrà chiesto il file sorgente (STL, OBJ o AMF) e, 
dopo la selezione, verrà richiesto dove salvare il file SVG di output. A questo 
punto, Slic3r genererà il file SVG.

Se si tenta di visualizzare il file SVG in un browser, verrà mostrato solo il primo 
layer e solo le "isole negative" all'interno del modello (poiché lo sfondo del 
browser è solitamente bianco).

![SVG nel
browser.](images/svg_output/svg_direct_browser.png "fig:")

Per questa ragione, è stata realizzata una piccola applicazione web che permette di 
visualizzare ogni singolo slice su uno sfondo nero[^1]. Basta aprire l'applicazione
e trascinare il file SVG nella finestra per caricarlo e visualizzarlo.

![Slic3r SVG
Viewer.](images/svg_output/svg_slic3rsvg_viewer.png "fig:")

## Impostazioni SVG

La maggior parte delle opzioni in Slic3r non è necessaria quando si genera un file 
SVG; tuttavia, il parametro `Layer height` determinerà il numero di layer. Si noti 
che Slic3r limita l’altezza del layer affinché sia inferiore al diametro dell’ugello, 
quindi tale valore potrebbe dover essere aumentato se si desiderano layer più alti.

## Stampare con SVG

Sebbene l'output SVG possa essere usato in diverse tipologie di stampanti, il seguente
esempio mostra come usare il file con una stampante DLP a resina. Utilizzando una
versione modificata di Printrun di Kliment[^2], il file SVG può essere caricato
direttamente e inviato a un proiettore DLP. L'asse Z è controllato tramite comandi
G-Code inviati attraverso il componente printcore, il che significa che è possibile
utilizzare l'elettronica standard RepRap, come RAMPS.

![Stampa di un file SVG con
Projectlayer.](images/svg_output/projectlayer.png "fig:")

[^1]: <http://garyhodgson.github.io/slic3rsvgviewer>  
[^2]: <http://garyhodgson.com/reprap/projectlayer>
