% L'importanza del primo layer

Prima di addentrarsi nella produzione della prima stampa, vale la pena fare una piccola deviazione per parlare dell'importanza di ottenere il primo layer nel modo giusto. Come molti hanno scoperto attraverso tentativi ed errori, se il primo layer non è il migliore possibile, può portare a un completo fallimento, parti che si staccano e deformazioni. Esistono diverse tecniche e raccomandazioni da seguire per minimizzare la possibilità che ciò accada.

#### Livellamento del Piano

Avere un piano livellato è fondamentale. Se la distanza tra la punta dell'ugello e il piano di stampa devia anche solo di una piccola quantità, può risultare in materiale che non si deposita correttamente sul piano (perché l'ugello è troppo vicino e raschia il piano) oppure il materiale si deposita troppo in alto rispetto al piano e non aderisce correttamente.

#### Temperatura Più Alta

L'hot-end dell'estrusore e il piano di stampa, se riscaldato, possono essere impostati a temperature più elevate per il primo layer, diminuendo così la viscosità del materiale estruso. Come regola empirica, si consiglia un aumento di 5°.

#### Velocità Più Bassa

Rallentare l'estrusore per il primo layer riduce le forze applicate al materiale fuso mentre esce dall'ugello, diminuendo le probabilità che venga allungato e non aderisca correttamente. Si raccomanda una velocità del 30% o del 50% rispetto alla velocità normale.

#### Tassi di Estrusione Calibrati Correttamente

Se viene estruso troppo materiale, l'ugello potrebbe trascinare il materiale già depositato durante il secondo passaggio, causando il distacco dal piano (soprattutto se il materiale si è raffreddato). Troppo poco materiale potrebbe far sì che il primo layer si stacchi durante la stampa, portando a oggetti staccati o deformazioni. Per questi motivi, è importante avere un tasso di estrusione ben calibrato come raccomandato in §[calibrazione].

#### Altezza del Primo Layer

Un'altezza di layer più spessa fornisce più flusso e, di conseguenza, più calore, rendendo l'estrusione più aderente al piano di stampa. Offre anche il vantaggio di maggiore tolleranza per il livellamento del piano. Si consiglia di aumentare l'altezza del primo layer per eguagliare il diametro dell'ugello, ad esempio un'altezza del primo layer di 0,35mm per un ugello da 0,35mm. **Nota:** L'altezza del primo layer viene impostata automaticamente in questo modo in modalità semplice.

#### Larghezza di Estrusione Maggiore

Più materiale tocca il piano, migliore sarà l'adesione dell'oggetto. Questo può essere ottenuto aumentando la larghezza di estrusione del primo layer, sia in percentuale che in quantità fissa. Eventuali spazi tra le estrusioni vengono regolati di conseguenza.

Si consiglia un valore di circa 200%, ma nota che il valore viene calcolato sull'altezza del layer e quindi dovrebbe essere impostato solo se l'altezza del layer è la più alta possibile. Ad esempio, se l'altezza del layer è 0,1mm e la larghezza di estrusione è impostata al 200%, la larghezza effettiva estrusa sarà solo 0,2mm, inferiore al diametro dell'ugello. Ciò causerebbe un flusso insufficiente e porterebbe a una stampa fallita. Pertanto, è altamente consigliato combinare la tecnica di altezza del primo layer elevata consigliata sopra con questa. Impostare l'altezza del primo layer a 0,35mm e la larghezza di estrusione del primo layer al 200% risulterà in un'estrusione spessa e bella larga 0,65mm.

#### Materiale del Piano di Stampa

Esistono molte opzioni per il materiale da utilizzare per il piano di stampa, e preparare la superficie giusta può migliorare notevolmente l'adesione del primo layer.

Il PLA è più indulgente e funziona bene su PET, Kapton o nastro adesivo blu per pittori.

L'ABS di solito necessita di maggior cura e, sebbene possa essere stampato bene su PET e Kapton, ci sono segnalazioni che le persone abbiano successo applicando lacca per capelli al piano di stampa prima della stampa. Altri hanno riportato che una slurry di ABS (realizzata dissolvendo un po' di ABS in acetone) applicata sottilmente può anche aiutare a mantenere la stampa attaccata.

#### Nessun Raffreddamento

Direttamente correlato a quanto sopra, non ha senso aumentare la temperatura del primo layer e avere ancora un ventilatore o un altro meccanismo di raffreddamento in funzione. È generalmente consigliato tenere il ventilatore spento per i primi strati.
