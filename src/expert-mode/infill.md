% Pattern e Densità del Riempimento

Quando si sceglie un pattern di riempimento, ci sono diversi fattori da considerare: la robustezza dell'oggetto, il tempo e il materiale richiesto, e le preferenze personali. È intuibile che un pattern più complesso richiederà più movimenti, aumentando così il tempo e il materiale necessari.

![Impostazioni del pattern di riempimento.](images/infill_pattern_settings.png "fig:")

Slic3r offre diversi pattern di riempimento: quattro regolari e tre più "esotici". I numeri riportati tra parentesi sotto ciascuna figura rappresentano una stima approssimativa del materiale utilizzato e del tempo impiegato per un modello semplice di un cubo da 20mm[^1]. Nota che questi dati sono solo indicativi, poiché la complessità del modello e altri fattori influenzano il tempo e il materiale.

-   **Line** (344.51mm / 5m:20s)  
    ![Pattern di riempimento: Line](images/infill_line.png "fig:")

-   **Rectilinear** (350.57mm / 5m:23s)  
    ![Pattern di riempimento: Rectilinear](images/infill_rectilinear.png "fig:")

-   **Concentric** (351.80mm / 5m:30s)  
    ![Pattern di riempimento: Concentric](images/infill_concentric.png "fig:")

-   **Honeycomb** (362.73mm / 5m:39s)  
    ![Pattern di riempimento: Honeycomb](images/infill_honeycomb.png "fig:")

-   **Hilbert Curve** (332.82mm / 5m:28s)  
    ![Pattern di riempimento: Hilbert Curve](images/infill_hilbertcurve.png "fig:")

-   **Archimedean Chords** (333.66mm / 5m:27s)  
    ![Pattern di riempimento: Archimedean Chords](images/infill_archimedeanchords.png "fig:")

-   **Octagram Spiral** (318.63mm / 5m:15s)  
    ![Pattern di riempimento: Octagram Spiral](images/infill_octagramspiral.png "fig:")

Certi tipi di modelli sono più adatti a un particolare pattern, ad esempio quelli organici rispetto a quelli meccanici. Nella figura seguente, il riempimento a nido d'ape (honeycomb) si adatta meglio a una parte meccanica, poiché ogni esagono si lega allo stesso pattern sottostante a ogni layer, formando una struttura verticale robusta.

![Confronto di pattern di riempimento in un oggetto complesso. Da sinistra a destra: honeycomb, line](images/complex_object_infill_comparison.png "fig:")

La maggior parte dei modelli richiede solo un riempimento a bassa densità, poiché una densità superiore al 50% produrrà un modello molto compatto che utilizza più materiale del necessario. Per questo motivo, un intervallo comune di densità varia tra il 10% e il 30%, ma i requisiti del modello determineranno quale densità sia la più adatta. La figura seguente mostra come i pattern cambiano con l'aumento della densità.

![Pattern di riempimento a densità variabile. Da sinistra a destra: 20%, 40%, 60%, 80%. Dall'alto verso il basso: Honeycomb, Concentric, Line, Rectilinear, Hilbert Curve, Archimedean Chords, Octagram Spiral](images/infills.png "fig:")

[^1]: Dati estratti da http://gcode.ws
