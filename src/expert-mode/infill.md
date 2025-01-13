% Pattern e Densità del Riempimento

La scelta di un pattern di riempimento dipende da diversi fattori: resistenza dell'oggetto, tempo e materiale, e preferenze personali. È evidente che un pattern più complesso richiede più movimenti, aumentando così il tempo e il materiale necessari.

![Impostazioni dei pattern di riempimento.](images/infill_pattern_settings.png "fig:")

Slic3r offre diversi pattern di riempimento, quattro regolari e tre più "esotici". I numeri indicati tra parentesi sotto ciascuna figura rappresentano una stima approssimativa del materiale usato e del tempo richiesto per un semplice modello a cubo di 20mm[^1]. Nota che questi valori sono solo indicativi, poiché la complessità del modello e altri fattori possono influenzare tempo e materiale.

- **Line (344.51mm / 5m:20s)**  
  ![Pattern di riempimento: Line](images/infill_line.png "fig:") 

- **Rectilinear (350.57mm / 5m:23s)**  
  ![Pattern di riempimento: Rectilinear](images/infill_rectilinear.png "fig:")

- **Concentric (351.80mm / 5m:30s)**  
  ![Pattern di riempimento: Concentric](images/infill_concentric.png "fig:")

- **Honeycomb (362.73mm / 5m:39s)**  
  ![Pattern di riempimento: Honeycomb](images/infill_honeycomb.png "fig:") 

- **Hilbert Curve (332.82mm / 5m:28s)**  
  ![Pattern di riempimento: Hilbert Curve](images/infill_hilbertcurve.png "fig:")

- **Archimedean Chords (333.66mm / 5m:27s)**  
  ![Pattern di riempimento: Archimedean Chords](images/infill_archimedeanchords.png "fig:")

- **Octagram Spiral (318.63mm / 5m:15s)**  
  ![Pattern di riempimento: Octagram Spiral](images/infill_octagramspiral.png "fig:")

### Applicazioni e Considerazioni

Alcuni tipi di modello si adattano meglio a un particolare pattern, ad esempio organici rispetto a quelli meccanici. L'immagine seguente mostra come un riempimento a nido d'ape sia più adatto a un componente meccanico, poiché ogni esagono si lega con lo stesso pattern sottostante a ogni layer, formando una struttura verticale resistente.

![Confronto dei pattern di riempimento in un oggetto complesso. Da sinistra a destra: honeycomb, line](images/complex_object_infill_comparison.png "fig:")

La maggior parte dei modelli richiede solo un riempimento a bassa densità, poiché superare, ad esempio, il 50% produce un modello molto compatto che utilizza più materiale del necessario. Per questo motivo, un range comune di densità va dal 10% al 30%. Tuttavia, i requisiti specifici del modello determineranno quale densità sia la migliore. La figura seguente mostra come i pattern cambiano all'aumentare della densità.

![Pattern di riempimento con densità variabili. Da sinistra a destra: 20%, 40%, 60%, 80%. Dall'alto verso il basso: Honeycomb, Concentric, Line, Rectilinear, Hilbert Curve, Archimedean Chords, Octagram Spiral](images/infills.png "fig:")

[^1]: Preso da http://gcode.ws
