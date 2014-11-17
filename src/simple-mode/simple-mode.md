% Modalità Semplificata

Slic3r ha due modalità di funzionamento, Semplificata e per Esperti. Queste possono essere scelte  dalla finestra delle `Preferenze` (che trovate sotto il menù `File`).

 ![Preferences.](images/preferences_general.png "fig:")


La Modalità Semplificata offre un ridotto Insieme di opzioni, abbastanza per chi è alle prime armi che vuole iniziare. La modalità esperti dà maggiore controllo su come Slic3r produce il G-code e verrà meglio approfondita più avanti.

Impostazioni di Stampa
--------------

La Scheda `Impostazioni di Stampa` fornisce la possibilità di modificare le impostazioni relative alla stampa attuale. Mentre le altre schede subiscono raramente cambiamenti,
le impostazioni su questa scheda verranno modificate regolarmente, probabilmente per ogni modello stampato.

[ht] ![Simple Mode: Print
Settings.](images/simple_mode_print_settings.png "fig:")


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

 ![Creating a vase from a solid
model.](images/solid_layers_vases.png "fig:")


#### Riempimento.

 `Riempire la Densità` è definito su una scala tra 0 e 1, dove 1 è il 100% e 0,4 sarebbe il 40%. Per la maggior parte dei casi non ha senso il 100% di riempimento in plastica del modello, ciò rappresenterebbe uno spreco di materiale ed impiegherebbe troppo tempo. Invece, molti modelli possono essere riempiti al loro interno con meno materiale e poi poi inseriti fra strati in materiale pieno al 100% (vedi sopra `Strati Solidi o Livelli Solidi`).

Un valore di densità del 0.4 è abbastanza per dare a qualsiasi modello una buona resistenza meccanica. Un valore di 0.2 è solitamente considerato il minimo richiesto a sostenere soffitti piani.

Slic3r offre diversi schemi di riempimento dei quali discuteremo meglio nella sezione di approfondimento - Scelte di Riempimento.
Scegliere uno `Schema di Riempimento` Dipenderà dal tipo di modello, dai desideri di robustezza strutturale, dalla velocità di stampa, e dal gusto personale del risultato che si vuole ottenere. I più esotici metodi di riempimento sono di solito troppo lenti e non necessariamente complessi per molti dei casi di uso, e così la maggior parte delle volte gli schemi di riempimento usati sono:
`rectilineare`, `linea`, or `nido d'ape`. Nido d'ape fornisce la maggior robustezza ma è più lento sia del metodo rettilineare che del metodo linea.

#### Materiale di Supporto.

 Stampare un modello dal basso verso l' alto, con una tecnica come l' FDM, significa che ogni sbalzo significativo verrà stampato nell' aria, è più probabilmente cadrà materiale (nel vuoto) e non stamperà correttamente. Scegliere materiale di supporto (`Opzione: Generare materiale di Supporto`) aggiungerà strutture addizionali attorno al modello che si accumula per poi sostenere la parte strutturale sovrastante. L' opzione `Schema di spaziamento o Pattern spacing` determina quanto deso il materiale di supporto deve essere nel venire stampato.

 ![An example of an object printed with support
material.](images/support_example.jpg "fig:")


Consiglio: It is sometimes worth considering altering the orientation of the
model in order to possibly reduce overhangs.

`Raft layers` will add additional layers underneath the model and stems
from the early days of 3D printing. It can help with prints without a
heated bed, or where the bed is not very flat, but it is usually not
required and is not recommended. The raft also requires post-processing
to remove it.

#### Speed.

 In simple mode there are only three speed settings
to consider:

-   `Perimeters` - The outline of the model may benefit from being
    printed slightly slower so that the outside skin of the print has
    fewer blemishes.

-   `Infill` - As the infill is hidden this can be extruded a little
    faster. Take care though not to go too fast as higher speeds results
    in thinner extrusions, and this may affect how the extrusions bond.

-   `Travel` - The jump between the end of one extrusion and the next
    should usually be performed as quickly as the printer will allow in
    order to minimise any mess caused by material oozing from the
    nozzle.

#### Brim.

 `Brim width` is used to add more perimeters to the
first layer, as a base flange, in order to provide more surface area for
the print to stick to the bed with in order to reduce warping (see
§). The brim is then cut away once the
print is finished and removed from the bed.

 ![An example of brim.](images/brim.jpg "fig:")


#### Sequential Printing.

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

Some common G-codes to use before the print starts are:

-   **G28** - Homes all the axes.

Some common G-codes to use after the print ends are:

-   **M104 S0** - Sets the extruder temperature to zero.

-   **M140 S0** - Sets the heated bed temperature to zero.

-   **G28 X0** - Home the X axis.

-   **M84** - Disables the motors.

[^1]: http://slic3r.org/blog/tip-printing-vases

[^2]: https://github.com/alexrj/Slic3r/wiki/FAQ\#what-placeholders-can-i-use-in-custom-g-code
