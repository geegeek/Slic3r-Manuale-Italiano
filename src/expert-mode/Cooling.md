% Cooling

La Temperatura gioca un ruolo chiave nel determinare la qualità di stampa. Troppo caldo ed 
il materiale si deformerà, troppo freddo e l' adesione tra gli strati risulterà problematica. 
Applicare il raffreddamento permetterà al materiale appena depositato di solidificare 
abbastanza da permettere una buona base per il prossimo strato, aiutando con 
gli strapiombi, piccoli dettagli e ponti.

Ci sono principalemte due tecniche per il reffreddamento: aggiungendo una ventola oppure rallentando 
la velocità di stampa. Sclic3r potrebbe scegliere di utilizzare entrambe le tecniche, utilizzando in primo luogo
la ventola, e rallentando la velocità di stampa se il tempo di deposito dello strato è troppo veloce.

 ![Cooling strategy.](images/cooling_chart.png "fig:")


La figura mostra la strategia adottata da Slic3r.
Leggendo da destra verso sinistra, quando la soglia minima della ventola (\#2) è
raggiunta la ventola viene spenta. Questa aumenta di intensità al diminuire del tempo di 
deposito dello strato. Il tempo di stampa resta costante finchè il The print speed remains constant until the estimated
print time drops below a certain threshold (\#1), this is when the print
speed is reduced until it reaches it’s minimum value.

Fans
----

 Most electronics and firmware allow the addition of a fan via
a spare connector. These can then be instructed with G-code, from
Slic3r, to turn on or off as the model requires, and to rotate at
different speeds.

Care should be taken with the positioning of the fan so that it does not
cool any heated bed more than necessary. It should also not cool the
heater block of the hot-end so as not to force it to do more work and
waste energy. The air movement should aim for the nozzle tip, flowing
over the freshly extruded material.

A duct may help in guiding the flow correctly, and there are several
designs available online, for a wide variety of printers.

Slowing Down
------------

 Slic3r can tell the printer to slow down if the
estimated layer time is above a certain threshold.

Care must be taken as the intended effect could be mitigated by the
nozzle not moving far enough away from the fresh extrusion, a problem
with small, detailed layers. For this reason it is usually recommended
to use a fan where possible.

Configuring
-----------



In simple mode Slic3r will attempt to choose the optimal settings for
both fans and speed. Expert mode gives more granular options.

 ![Cooling advanced
settings.](images/cooling_advanced_settings.png "fig:")


-   `Fan speed` - Determines the minimum and maximum speeds - useful for
    fans that run too fast by default.

-   `Bridges fan speed` - As the material stretches over wide gaps, it
    makes sense to try and cool it as much as possible, therefore a full
    fan speed is recommended.

-   `Disable fan for first n layers` - Section
     detailed how important the first
    layer is, and so it makes sense not to apply the fan until sure the
    print is securely attached to the bed. Keeping the fan turned off
    for the first two or three layers is a good idea.

-   `Keep fan always on` - Overrides any other choices and has the fan
    run continuously, at least at the minimum speed setting. This can be
    useful when printing with PLA, but is not recommended for ABS.

-   `Enable fan if print time is below t seconds` - Triggers the fan if
    the layer will be completed within the given number of seconds.

-   `Slow down if layer print time is below t seconds` - Slows down the
    print if the layer will be completed within the given number of
    seconds.

-   `Min print speed` - A lower limit on how slowly a layer can be
    printed.


