% Modalità Semplificata

Slic3r ha due modalità di funzionamento, Semplificata e per Esperti. Queste possono essere scelte  dalla finestra delle `Preferenze` (che trovate sotto il menù `File`).

 ![Preferenze.](images/preferences_general.png "fig:")


La Modalità Semplificata offre un ridotto Insieme di opzioni, abbastanza per chi è alle prime armi che vuole iniziare. La modalità esperti dà maggiore controllo su come Slic3r produce il G-code e verrà meglio approfondita più avanti.

Impostazioni di Stampa
--------------

La Scheda `Impostazioni di Stampa` fornisce la possibilità di modificare le impostazioni relative alla stampa attuale. Mentre le altre schede subiscono raramente cambiamenti,
le impostazioni su questa scheda verranno modificate regolarmente, probabilmente per ogni modello stampato.

[ht] ![Modalità Semplificata: Impostazioni di Stampa.](images/simple_mode_print_settings.png "fig:")


#### Generale.



`Altezza del livello è lo spessore di ogni livello, ed è il passo che l' asse verticale realizza prima di estrudere un nuovo livello sopra il precedente. Ci sono diversi fattori che influenzano il qunato alto deve essere ogni livello:

-   **Desiderio di risoluzione** - Un livello più alto dovrebbe risultare nella stampa con venature e bordimeno visibili, proprio perchè ogni livello è più piccolo.
    L' estetica gioca un roulo importante in questo aspetto, ma anche il tipo di modello, per esempio , una parte meccanica può non richiedere una risoluzione a così alta finitura, mentre un pezzo da esposizione si.

-   **Velocità di stampa** - Livelli più corti si tradurranno in risultati di stampa più accurati ma ogni stampa impiegherà di più, semplicemente perchè l' estrusore dovrà tracciare il percorso del modello più volte. Un obiettivo in seguito sarà quello di trovare per la propria stampante un compromesso tra l' Altezza del livello, la velocità di stampa della stampante, e la qualità del prodotto finito.

`Il Perimetro definisce il numero minimo di scaffalature verticali ( cioè Muri) che una stampa dovrà avere. A meno che il modello richieda un unico muro largo è generalmente raccomandato di avere un minimo di 2 perimetri in modo da dare un minimo di garanzia che se una sezione del perimetro non è stampata correttamente allora il secondo perimetro aiuterà a coprirla.

Gli strati (livelli) estremi superiori ed inferiori che racchiudono il modello sono riempiti con un `Trama a riempimento solido`. Per i livelli estremi inferiori il fattore importante da considerare è come la superficie che appare sembrerà se ci fosse un errore nel depositare il filamento del primo strato (livello), e per questa ragione è raccomandato di impostare almeno 2 livelli inferiori.

Una considerazione simile è richiesta per gli strati superiori. In qunato gli strati intermedi verranno riempiti con uno schema pre-impostato e questo può richiedere più di un passaggio per coprirlo completamente.

 ![An example of insufficient top
layers.](images/bad_top_infill.jpg "fig:") 

Un altro consiglio da considerare: Impostare gli strati estremi superiori a zero, ed impostare anche un piempimento pari a zero, ciò si tradurra in un recipiente cavo, ideale per convertire i vostri modelli per esempio in vasi[^1]. Qui per esempio una manipolazione delle impostazioni all' interno di Slic3r può essere usata per generare differenti tipi di stampe, e non solo per controllare l' accuratezza di stampa.

 ![Creazione di un vaso da un modello solido.](images/solid_layers_vases.png "fig:")


#### Riempimento.

 `Riempire la Densità` è definito su una scala tra 0 e 1, dove 1 è il 100% e 0,4 sarebbe il 40%. Per la maggior parte dei casi non ha senso il 100% di riempimento in plastica del modello, ciò rappresenterebbe uno spreco di materiale ed impiegherebbe troppo tempo. Invece, molti modelli possono essere riempiti al loro interno con meno materiale e poi poi inseriti fra strati in materiale pieno al 100% (vedi sopra `Strati Solidi o Livelli Solidi`).

Un valore di densità del 0.4 è abbastanza per dare a qualsiasi modello una buona resistenza meccanica. Un valore di 0.2 è solitamente considerato il minimo richiesto a sostenere soffitti piani.

Slic3r offre diversi schemi di riempimento dei quali discuteremo meglio nella sezione di approfondimento - Scelte di Riempimento.
Scegliere uno `Schema di Riempimento` Dipenderà dal tipo di modello, dai desideri di robustezza strutturale, dalla velocità di stampa, e dal gusto personale del risultato che si vuole ottenere. I più esotici metodi di riempimento sono di solito troppo lenti e non necessariamente complessi per molti dei casi di uso, e così la maggior parte delle volte gli schemi di riempimento usati sono:
`rectilineare`, `linea`, or `nido d'ape`. Nido d'ape fornisce la maggior robustezza ma è più lento sia del metodo rettilineare che del metodo linea.

#### Materiale di Supporto.

 Stampare un modello dal basso verso l' alto, con una tecnica come l' FDM, significa che ogni sbalzo significativo verrà stampato nell' aria, è più probabilmente cadrà materiale (nel vuoto) e non stamperà correttamente. Scegliere materiale di supporto (`Opzione: Generare materiale di Supporto`) aggiungerà strutture addizionali attorno al modello che si accumula per poi sostenere la parte strutturale sovrastante. L' opzione `Schema di spaziamento o Pattern spacing` determina quanto deso il materiale di supporto deve essere nel venire stampato.

 ![Un esempio di oggestto stampato con il materiale di supporto.](images/support_example.jpg "fig:")


Consiglio: Talvolta è opportuno considerare di modificare l' orientazione del modello in modo da diminuire le possibilità che si verifichino sbalzi nel vuoto. Ad esempio molti modelli disegnati per l' FDM sono concepiti per avere un lato di stampa ottimale per la riduzione di tale fenomeno.

Nel seguente esempio, il modello è stato realizzato tenendo conto degli sbalzi nel vuoto e minimizzado il più possibile questa possibilità. In aggiunta ulteriori parti (che poi verranno facilmente rimosse) , come quella evidenziata, sono state concepite per garantire una buona stampa senza gli strati di supporto. In questo caso il modello presenta una tendenza ad essere stampato in un particolare verso di stampa che è quello in figura.

![Un esempio di un oggetto che và stampato seguento un preciso orientamento di stampa.](images/I2-wade.png "fig:")


`Livello Letto di Stampa` aggiungerà ulteriori livelli sotto il modello di stampa e tale opzione esiste sin dai primi giorni della stampa 3D. Questa opzione può aiutare con stampe senza un letto riscaldato, oppure dove il letto non è propriamente piatto, ma solitamente non è necessaria e nemmeno raccomandata. I Livelli di Letto di Stampa richiedono in post-produzione una rimozione manuale dal modello appena stampato.

#### Velocità.

In modo semplice ci sono solo tre impostazioni di velocità da considerare:

-   `Perimetri` - Le linee esterne del modello possono beneficiare dall' essere stampate con maggiore lentezza così che la superficie esterna del modello appaia con minori imperfezioni.

-   `Riempimento` - Dato che il riempimento è nascosto esso può essere estruso ad una velocità più rapida. Fate attenzione però a non andare troppo    	     velocemente poichè velocità più elevate portano ad estrusioni più sottili del materiale, e ciò può influenzare il modo il cui la struttura di              riempento si lega.

-   `Viaggio a vuoto` - Il salto tra la fine di una lina di estrusione e l' inizio di una prossima estrusione dovrebbe solitamente essere eseguito alla massima velocità che la stampante è in grado di eseguire in modo da minimizzare il disordine causato dal trasudamento di materiale dall' augello in temperatura.

#### Gonna.

 `Larghezza Gonna` Questa opzione viene usata per aggiungere ulteriori perimetri al primo livello, come una flangia, in modo da fornire una maggiore superficie di base e migliorare le possibilità che la stampa si attacchi meglio al piatto di stampa e ridurre quindi la deformazione causata dal raffreddamento (vedi
§). La Gonna è poi tagliata via una volta che la stampa è terminata e rimosse tutte le eccedenze dal piatto di stampa.

 ![Un esempio di gonna.](images/brim.jpg "fig:")


#### Stampa Sequenziale.

 This feature allows to compose a plate of
objects but have the printer complete each one individually before going
back to Z = 0 and starting with the next one. See the section about
Sequential Printing in the Advanced Topics chapter.

Filament Settings
-----------------

The `Filament Settings` will normally be used infrequently, for example
on receipt of a new roll of filament.

 ![Simple Mode: Filament
Settings.](images/simple_mode_filament_settings.png "fig:")


#### Filament.

 The `Diameter` setting will already have been filled from
the value given during the wizard (see p.), but can be updated here.

The `Extrusion multiplier` setting allows the fine tuning of the
extrusion flow rate, and is is given as a factor, e.g. 1 means 100%, 1.5
would mean 150%. Whilst the value should ideally be set in the firmware
it can be useful to test slight changes to the rate by altering this
value. It varies the amount of plastic proportionally and should be
changed in very small steps (e.g. +/- 0.05) as the effects are very
visible.

#### Temperature.

 These values are also filled from the wizard, but here
the opportunity exists to set the temperature for the first layer (see
p.).

Printer Settings
----------------

The `Printer Settings` will be updated the least, unless Slic3r is going
to be used for many printers, for example, in a 3D printer farm.

 ![Simple Mode: Printer
Settings.](images/simple_mode_printer_settings.png "fig:")


#### Size and coordinates.

 The `Bed size` setting is taken from the
wizard (see p.) and is only used for previewing the model in the plater.

The `Print center` is the point around which the print will be centered.
A `Bed size` of 200mmx200mm and a `Print center` of 100mmx100mm would
sit the print in the middle. Should it be desired to print away from the
center, because of a scratch in the glass perhaps, then this option
should be used.

`Z offset` can be used to compensate for an incorrectly calibrated Z
end-stop. If the nozzle stops slightly too far from the bed, then adding
a negative value will offset all layers by that amount. The correct
solution however is to fix the end-stop itself.

The optimal Z endstop position is where the nozzle tip barely touches
the surface of the bed when homed. A sheet of paper makes a good gauge
for this very small distance. It is not recommended to use this setting
to try and improve layer adhesion, by "squashing" the bottom layer into
the bed, instead look at the suggestions in section
.

#### Firmware.

 As selected in the wizard (see p.), `G-code flavour`
defines the dialect of G-code generated.

#### Extruder.

 `Nozzle diameter` was defined in the wizard (see p.).

#### Retraction.

 Unless the material being extruded has a very high
viscosity it may ooze between extrusions due to gravity. This can be
remedied by actively retracting the filament between extrusions. Setting
the `Length` parameter to a positive value will cause the filament to be
reversed by that many millimeters before travel. The retraction will
then be compensated for by the same amount after the travel move, before
starting the new extrusion path.

A value of between 1 and 2mm is usually recommended. Bowden extruders
may need up to 4 or 5mm due to the hysteresis introduced by the tube.
Setting the `Lift Z` parameter to a positive value will raise the entire
extruder on the Z axis by that many millimeters during each travel. This
can be useful to ensure the nozzle will not catch on any already laid
filament, however it is usually not necessary and will slow the print
speed. A value of 0.1mm is usually sufficient.

#### Start, End and Layer Chance G-codes.

 Custom G-code commands can be run before a print
starts and after a print finishes.

Placeholders can be inserted in the G-code commands[^2]. For example
[next\_extruder] would return the index of the next extruder.

The RepRap wiki is a good resource to learn about the variety of G-codes
available: `http://reprap.org/wiki/G-code`.

Note: Be sure to check that a given G-code is valid for your firmware.

The codes specified in `Start G-code` are inserted at the beginning of
the output file, directly after the temperature control commands for
extruder and bed. Note that if temperature control commands are
specified (M104 and M190) then these will replace the temperature
G-codes introduced by the `Filament` settings.

Alcuni dei G-code utilizzati prima dell' inizio di una stampa sono:

-   **G28** -  Porta la stampante all' Origine 'O' di tutti gli assi.

Alcuni dei G-code utilizzati dopo il termine di una stampa sono:

-   **M104 S0** - Imposta la temperatura dell' estrusore a zero (disabilita il riscaldamento).

-   **M140 S0** - Imposta il letto di stampa riscaldato a zero (disabilita il riscaldamento).

-   **G28 X0** - Porta la stampante all' Origine 'O' del solo asse X.

-   **M84** - Disabilita i motori passo passo.

[^1]: http://slic3r.org/blog/tip-printing-vases

[^2]: https://github.com/alexrj/Slic3r/wiki/FAQ\#what-placeholders-can-i-use-in-custom-g-code
