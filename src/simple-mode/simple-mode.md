% Modalità Semplificata

Slic3r ha due modalità di funzionamento, Semplificata e per Esperti. Queste possono essere scelte dalla finestra delle `Preferenze` (che trovate sotto il menù `File`).

![Preferenze.](images/preferences_general.png "fig:")


La Modalità Semplificata offre un ridotto Insieme di opzioni, abbastanza per chi è alle prime armi che vuole iniziare. La modalità esperti dà maggiore controllo su come Slic3r produce il G-code e verrà meglio approfondita più avanti.

Impostazioni di Stampa
--------------

La Scheda `Impostazioni di Stampa` fornisce la possibilità di modificare le impostazioni relative alla stampa attuale. Mentre le altre schede subiscono raramente cambiamenti,
le impostazioni su questa scheda verranno modificate regolarmente, probabilmente per ogni modello stampato.

[ht] ![Modalità Semplificata: Impostazioni di Stampa.](images/simple_mode_print_settings.png "fig:")


#### Generale.



`Altezza del livello è lo spessore di ogni livello, ed è il passo che l' asse verticale realizza prima di estrudere un nuovo livello sopra il precedente. Ci sono diversi fattori che influenzano il quanto alto deve essere ogni livello:

- **Desiderio di risoluzione** - Un livello più alto dovrebbe risultare nella stampa con venature e bordi meno visibili, proprio perché ogni livello è più piccolo.
L' estetica gioca un ruolo importante in questo aspetto, ma anche il tipo di modello, per esempio , una parte meccanica può non richiedere una risoluzione a così alta finitura, mentre un pezzo da esposizione si.

- **Velocità di stampa** - Livelli più corti si tradurranno in risultati di stampa più accurati ma ogni stampa impiegherà di più, semplicemente perché l' estrusore dovrà tracciare il percorso del modello più volte. Un obiettivo in seguito sarà quello di trovare per la propria stampante un compromesso tra l' Altezza del livello, la velocità di stampa della stampante, e la qualità del prodotto finito.

`Il Perimetro definisce il numero minimo di scaffalature verticali ( cioè Muri) che una stampa dovrà avere. A meno che il modello richieda un unico muro largo è generalmente raccomandato di avere un minimo di 2 perimetri in modo da dare un minimo di garanzia che se una sezione del perimetro non è stampata correttamente allora il secondo perimetro aiuterà a coprirla.

Gli strati (livelli) estremi superiori ed inferiori che racchiudono il modello sono riempiti con un `Trama a riempimento solido`. Per i livelli estremi inferiori il fattore importante da considerare è come la superficie che appare sembrerà se ci fosse un errore nel depositare il filamento del primo strato (livello), e per questa ragione è raccomandato di impostare almeno 2 livelli inferiori.

Una considerazione simile è richiesta per gli strati superiori. In quanto gli strati intermedi verranno riempiti con uno schema pre-impostato e questo può richiedere più di un passaggio per coprirlo completamente.
![Un esempio di strato superiore non sufficiente.](images/bad_top_infill.jpg "fig:") 

Un altro consiglio da considerare: Impostare gli strati estremi superiori a zero, ed impostare anche un riempimento pari a zero, ciò si tradurrà in un recipiente cavo, ideale per convertire i vostri modelli per esempio in vasi[^1]. Qui per esempio una manipolazione delle impostazioni all' interno di Slic3r può essere usata per generare differenti tipi di stampe, e non solo per controllare l' accuratezza di stampa.

![Creazione di un vaso da un modello solido.](images/solid_layers_vases.png "fig:")


#### Riempimento.

`Riempire la Densità` è definito su una scala tra 0 e 1, dove 1 è il 100% e 0,4 sarebbe il 40%. Per la maggior parte dei casi non ha senso il 100% di riempimento in plastica del modello, ciò rappresenterebbe uno spreco di materiale ed impiegherebbe troppo tempo. Invece, molti modelli possono essere riempiti al loro interno con meno materiale e poi poi inseriti fra strati in materiale pieno al 100% (vedi sopra `Strati Solidi o Livelli Solidi`).

Un valore di densità del 0.4 è abbastanza per dare a qualsiasi modello una buona resistenza meccanica. Un valore di 0.2 è solitamente considerato il minimo richiesto a sostenere soffitti piani.

Slic3r offre diversi schemi di riempimento dei quali discuteremo meglio nella sezione di approfondimento - Scelte di Riempimento.
Scegliere uno `Schema di Riempimento` Dipenderà dal tipo di modello, dai desideri di robustezza strutturale, dalla velocità di stampa, e dal gusto personale del risultato che si vuole ottenere. I più esotici metodi di riempimento sono di solito troppo lenti e non necessariamente complessi per molti dei casi di uso, e così la maggior parte delle volte gli schemi di riempimento usati sono:
`rettilineare`, `linea`, or `nido d'ape`. Nido d'ape fornisce la maggior robustezza ma è più lento sia del metodo rettilineare che del metodo linea.

#### Materiale di Supporto.

Stampare un modello dal basso verso l' alto, con una tecnica come l' FDM, significa che ogni sbalzo significativo verrà stampato nell' aria, è più probabilmente cadrà materiale (nel vuoto) e non stamperà correttamente. Scegliere materiale di supporto (`Opzione: Generare materiale di Supporto`) aggiungerà strutture addizionali attorno al modello che si accumula per poi sostenere la parte strutturale sovrastante. L' opzione `Schema di spaziamento o Pattern spacing` determina quanto denso il materiale di supporto deve essere nel venire stampato.

![Un esempio di oggetto stampato con il materiale di supporto.](images/support_example.jpg "fig:")


Consiglio: Talvolta è opportuno considerare di modificare l' orientazione del modello in modo da diminuire le possibilità che si verifichino sbalzi nel vuoto. Ad esempio molti modelli disegnati per l' FDM sono concepiti per avere un lato di stampa ottimale per la riduzione di tale fenomeno.

Nel seguente esempio, il modello è stato realizzato tenendo conto degli sbalzi nel vuoto e minimizzando il più possibile questa possibilità. In aggiunta ulteriori parti (che poi verranno facilmente rimosse) , come quella evidenziata, sono state concepite per garantire una buona stampa senza gli strati di supporto. In questo caso il modello presenta una tendenza ad essere stampato in un particolare verso di stampa che è quello in figura.

![Un esempio di un oggetto che va stampato seguendo un preciso orientamento di stampa.](images/I2-wade.png "fig:")


`Livello Letto di Stampa` aggiungerà ulteriori livelli sotto il modello di stampa e tale opzione esiste sin dai primi giorni della stampa 3D. Questa opzione può aiutare con stampe senza un letto riscaldato, oppure dove il letto non è propriamente piatto, ma solitamente non è necessaria e nemmeno raccomandata. I Livelli di Letto di Stampa richiedono in post-produzione una rimozione manuale dal modello appena stampato.

#### Velocità.

In modo semplice ci sono solo tre impostazioni di velocità da considerare:

- `Perimetri` - Le linee esterne del modello possono beneficiare dall' essere stampate con maggiore lentezza così che la superficie esterna del modello appaia con minori imperfezioni.

- `Riempimento` - Dato che il riempimento è nascosto esso può essere estruso ad una velocità più rapida. Fate attenzione però a non andare troppo velocemente poiché velocità più elevate portano ad estrusioni più sottili del materiale, e ciò può influenzare il modo il cui la struttura di riempimento si lega.

- `Viaggio a vuoto` - Il salto tra la fine di un percorso di estrusione e l' inizio di una prossima estrusione dovrebbe solitamente essere eseguito alla massima velocità che la stampante è in grado di eseguire in modo da minimizzare il disordine causato dalla fuoriuscita di materiale dall' ugello in temperatura.

#### Gonna.

`Larghezza Gonna` Questa opzione viene usata per aggiungere ulteriori perimetri al primo livello, come una flangia, in modo da fornire una maggiore superficie di base e migliorare le possibilità che la stampa si attacchi meglio al piatto di stampa e ridurre quindi la deformazione causata dal raffreddamento (vedi
§). La Gonna è poi tagliata via una volta che la stampa è terminata e rimosse tutte le eccedenze dal piatto di stampa.

![Un esempio di gonna.](images/brim.jpg "fig:")


#### Stampa Sequenziale.

Questa caratteristica permette di comporre un piatto di oggetti ma di avere la stampa completa di ogni oggetto prima di resettare Z=0 ed iniziare con il prossimo oggetto. Vedere la sezione sulla Stampa Sequenziale nel capitolo delle Argomentazioni Avanzate.

Impostazioni Filamento
-----------------

Le `Impostazioni Filamento` di norma verranno utilizzate con poca frequenza, per esempio alla ricezione di una nuova bobina di filamento.

![Simple Mode: Filament
Settings.](images/simple_mode_filament_settings.png "fig:")


#### Filamento.

Le impostazioni di `Diametro` saranno già state compilate durante la procedura guidata (vedi p.), ma possono essere aggiornate anche 
successivamente in questa sezione.

L' impostazione `Estrusori Multipli` permette una messa a punto fino del flusso di estrusione, ed è espressa come fattore, esempio 1 significa 
100%, 1,5 significherà 150%. Mentre il valore dovrebbe idealmente essere impostato nel firmware può essere utile impostare lievi cambiamenti al 
flusso di estrusione alterando questo valore. Essa varia proporzionalmente la quantità di plastica e dovrebbe essere modificato in piccoli 
passi (e.g. +/- 0.05) in modo che gli effetti siano molto visibili.

#### Temperatura.

Questi valori sono anche stati compilati all' interno della procedura guidata, ma qui esiste anche la possibilità d' impostare la temperatura 
per il primo strato (vedi p.).

Impostazioni Stampante
----------------

Le `Impostazioni Stampante` verranno variate il meno possibile, a meno che Slic3r venga utilizzato per diverse stampanti, per esempio, in un 
centro di stampanti 3d.

![Simple Mode: Printer
Settings.](images/simple_mode_printer_settings.png "fig:")


#### Dimensioni e Coordinate.

L' impostazione `Dimensione letto di stampa` è anch' essa compilata durante la procedura guidata (vedi p.) e viene usata solo per la 
visualizzazione dell' anteprima del modello in corso.

Il `Centro di Stampa` è il punto attorno al quale la stampa verrà centrata.
Per un `Letto di Stampa` di 200mmx200mm ed un `Centro di Stampa` di 100mmx100mm posizionerà la stampa nel centro.
Se di desiderasse stampare lontano dal centro, ad esempio a causa di un graffio sul vetro, allora si dovrebbe utilizzare questa opzione.

`Z offset` può essere utilizzata per compensare una errata calibrazione dell' interruttore di fine corsa dell' asse Z. Se l' ugello si posiziona leggermente troppo lontano dal letto di stampa, allora aggiungere un valore negativo compenserà tutti gli strati mancanti di quella distanza. La soluzione corretta è comunque quella di correggere lo stesso interruttore di fine corsa.

La posizione ottimale dell' interruttore di fine corsa dell' asse Z è quella in cui la punta dell' ugello tocca a malapena la superficie del letto di stampa quando posizionato all' origine. Un foglio di carta può essere usato come calibro per questa piccola distanza. Non è raccomandato utilizzare questa impostazione per migliorare l' adesione del primo strato "spiaccicando" il primo strato sul letto di stampa, invece per migliorare questo aspetto guardate i suggerimenti nella sezione appropriata.

#### Firmware.

E' stato già selezionato durante la procedura guidata (vedi p.), `G-code flavour`
definisce il linguaggio specifico del G-code generato.

#### Estrusore.

Il `Diametro dell' ugello` è stato definito durante la procedura guida (vedi p.).

#### Ritrazione.

A meno che il materiale estruso abbia una viscosità molto alta esso può uscire fuori tra un estrusione ed un altra a causa della gravità. A ciò vi si può porre rimedio attivando la retrazione del filamento tra una estrusione ed un altra. Impostando il parametro 'Distanza' ad un valore positivo permetterà che il filamento venga retratto di qualche millimetro nello spostamento a vuoto tra un' estrusione ed un altra. Terminato lo spostamento a vuoto la retrazione riporterà il filamento alla stessa posizione precedente e riprenderà un nuovo percorso di estrusione.

Un valore tra 1 e 2mm è solitamente consigliato. Gli estrusori tipo Bowden potrebbero avere bisogno anche di 4 o 5mm a causa della isteresi introdotta dal tubo.
Impostare il parametro `Lift Z` (ascensore Z) ad un valore positivo alzerà tutto il blocco estrusore sull' asse Z di quella quantità per ogni viaggio a vuoto. Questo può essere utile per assicurarsi che l' ugello durante i suoi movimenti non urti e quindi sposti nessun filamento già deposto. Un valore di 0.1mm è solitamente più che sufficiente.

#### G-code di Inizio e Fine stampa.

G-code personalizzati possono essere eseguiti prima dell' inizio di una stampa e successivamente dal suo termine.

Segnaposto possono essere inseriti nei comandi G-code [^2]. Per esempio
[next\_extruder] restituirà l' indice del prossimo estrusore.

Il wiki di RepRap è un ottima risorsa dalla quale apprendere la varietà di G-code
disponibili: `http://reprap.org/wiki/G-code`.

Nota bene: Assicurati di controllare che un determinato G-code sia valido per il tuo firmware.

I codici specificati in `Start G-code` verranno inseriti all' inizio
del file di output, direttamente dopo i comandi di controllo della temperatura per
l' estrusore ed il letto di stampa. Nota che se i comandi di controllo della temperatura vengono 
specificati (M104 and M190) allora questi rimpiazzeranno i G-code di temperatura
 introdotti dalle impostazioni del `Filament`.

Alcuni dei G-code utilizzati prima dell' inizio di una stampa sono:

- **G28** - Porta la stampante all' Origine 'O' di tutti gli assi.

Alcuni dei G-code utilizzati dopo il termine di una stampa sono:

- **M104 S0** - Imposta la temperatura dell' estrusore a zero (disabilita il riscaldamento).

- **M140 S0** - Imposta il letto di stampa riscaldato a zero (disabilita il riscaldamento).

- **G28 X0** - Porta la stampante all' Origine 'O' del solo asse X.

- **M84** - Disabilita i motori passo passo.

[^1]: http://slic3r.org/blog/tip-printing-vases

[^2]: https://github.com/alexrj/Slic3r/wiki/FAQ\#what-placeholders-can-i-use-in-custom-g-code

