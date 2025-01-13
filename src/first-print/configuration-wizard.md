% Procedura Guidata di Configurazione

Slic3r offre due funzionalità per aiutare i nuovi utenti: la procedura guidata di configurazione e la modalità semplice.

A volte è utile avere una mano quando si inizia a utilizzare un nuovo software. La procedura guidata di configurazione pone una serie di domande e crea una configurazione iniziale per Slic3r.

![Wizard di Configurazione: Schermata di Benvenuto](images/configuration-wizard/configuration_wizard_welcome.png "fig:")

### 1. Tipo di Firmware

Il G-code prodotto da Slic3r è adattato a particolari tipi di firmware. Il primo passaggio richiede di specificare il firmware utilizzato dalla stampante. Questo dovrebbe essere stato specificato durante la costruzione o la configurazione della stampante. Se non sei sicuro, contatta il fornitore.

![Wizard di Configurazione: Tipo di Firmware](images/configuration-wizard/configuration_wizard_firmware_type.png "fig:")

### 2. Dimensione del Piano

Questa impostazione definisce la distanza massima che l'estrusore può percorrere lungo gli assi X e Y. Se le dimensioni non sono facilmente disponibili per la stampante, possono essere facilmente misurate.

Assicurati di misurare dall'angolo in basso a sinistra dove l'ugello dell'estrusore si trova nella posizione di home fino alla distanza massima che l'ugello può percorrere in ciascuna direzione. Considera che il carrello X potrebbe toccare il telaio prima che l'ugello raggiunga la distanza massima, questo dipende dal modello e dalla marca della stampante.

Ricorda anche di controllare eventuali impostazioni dei finecorsa nel firmware che potrebbero limitare il movimento degli assi X/Y.

![Wizard di Configurazione: Dimensione del Piano](images/configuration-wizard/configuration_wizard_bed_size.png "fig:")

### 3. Diametro dell'Ugello

Il diametro dell'ugello del hot-end è solitamente chiaramente indicato nella descrizione del hot-end o nella documentazione associata al momento dell'acquisto. Valori comuni sono 0,5mm e 0,35mm.

Se l'ugello è stato realizzato in casa o proviene da una fonte senza un diametro specificato, misura con attenzione l'apertura il più accuratamente possibile. Un modo per determinare la dimensione dell'ugello è estrudere lentamente (1mm/s) del filamento nell'aria libera e misurare lo spessore dell'estrusione risultante[^1]. Questo metodo tiene conto dell'espansione del materiale durante l'estrusione, e può essere utile anche se il diametro è noto.

![Wizard di Configurazione: Diametro dell'Ugello](images/configuration-wizard/configuration_wizard_nozzle_diameter.png "fig:")

### 4. Diametro del Filamento

Per ottenere risultati accurati, Slic3r deve conoscere con precisione quanto materiale viene spinto attraverso l'estrusore. È quindi fondamentale fornire un valore il più preciso possibile per il diametro del filamento.

Sebbene il filamento utilizzato nelle stampanti FDM sia venduto con diametri standard di 3mm o 1,75mm, questa è solo una guida generale. Il diametro può variare tra diversi produttori e persino tra diversi lotti. Pertanto, è altamente consigliato prendere più misurazioni lungo una lunghezza di filamento e usare la media. Ad esempio, misurazioni di 2,89mm, 2,88mm, 2,90mm e 2,91mm produrrebbero una media di 2,895mm, che dovrebbe essere utilizzata.

![Wizard di Configurazione: Diametro del Filamento](images/configuration-wizard/configuration_wizard_filament_diameter.png "fig:")

### 5. Temperatura di Estrusione

La temperatura di estrusione dipende dal materiale, e la maggior parte dei materiali può operare in un intervallo di temperature. Il fornitore dovrebbe fornire indicazioni sulle temperature adatte. Una regola empirica molto generale è che il PLA si trova tra 160°C e 230°C, mentre l'ABS tra 215°C e 250°C. Materiali più esotici avranno intervalli diversi.

Questo è uno dei parametri che vorrai ottimizzare quando inizi a produrre stampe. La temperatura ottimale può variare anche tra diversi colori dello stesso materiale. Un altro fattore che può influenzare la temperatura scelta è la velocità di estrusione, dove generalmente una estrusione più rapida richiede temperature più elevate.

**Nota:** È possibile controllare manualmente la temperatura dell'estrusore dal controller della stampante. In questo caso, la temperatura può essere impostata a zero.

![Wizard di Configurazione: Temperatura di Estrusione](images/configuration-wizard/configuration_wizard_extrusion_temperature.png "fig:")

### 6. Temperatura del Piano di Stampa

Se la stampante è dotata di un piano di stampa riscaldato, questo parametro può essere impostato. Come per la temperatura dell'estrusore, il valore dipenderà dal materiale utilizzato. Una regola empirica è che il PLA richiede circa 60°C e l'ABS circa 110°C.

**Nota:** È possibile controllare manualmente la temperatura del piano di stampa dal controller della stampante. In questo caso, la temperatura può essere impostata a zero.

![Wizard di Configurazione: Temperatura del Piano di Stampa](images/configuration-wizard/configuration_wizard_bed_temperature.png "fig:")

A questo punto, la procedura guidata è completata e la configurazione di base è definita.

![Wizard di Configurazione: Fine](images/configuration-wizard/configuration_wizard_end.png "fig:")

[^1]: <http://forums.reprap.org/read.php?1,113374,113953>
