% Utilizzo da Linea di Comanado
Quasi tutte le caratteristiche di Slic3r possono essere accedute da linea di comando.Puoi quindi
chiamare Slic3r come parte di uno script o installarlo su un sistema embedded o un server remoto.

Per ottenere l'elenco completo ed i riferimenti dei comandi disponibili da linea
di comando, basta eseguire:

    slic3r --help

**Nota:** potresti avere bisogno di sostituire `slic3r` con il nome e/o il percorsodell'eseguibile di Slic3r che potrebbe essere:

* `slic3r-console.exe` su Windows
* `slic3r` su GNU/Linux
* `Slic3r.app/Contents/MacOS/slic3r` su MacOS X
* `perl slic3r.pl` su tutte le piattaforme, se si sta eseguendo da Git da codice sorgente.

Generare G-code
-----------------
Per convertire un modello in G-code hai bisogno di fornirgli il file STL, insieme a qualsiasi configurazione intendi utilizzare:

    slic3r my_model.stl --layer-height 0.2
Questo genererà un file denominato *mio_modello.gcode* nella stessa cartella
 del file STL di input. Si consiglia di specificare un percorso di output personalizzato:

    slic3r mio_modello.stl --layer-height 0.2 --output /percorso/di/output.gcode


L'argomento per `--output`può anche essere una cartella;in questo caso il file
assumerà lo schema di nominazione automatica (che può essere sovrascritta utilizzando l'opzione
`--output-filename-format` ; vedere il capitolo apposito).

### Configurazione

**Nota:**  le impostazioni base di stampa del filamento/stampa/stampante definite nell' interfaccia grafica vengono completamente ignorati quando si eseguono comandi nella modalità linea di comando. Slic3r verrà sempre settato alle sue impostazioni di default.

Avrai bisogno di esportare la tua configurazione desiderata con il comando *Export Config...*,
che è collocato nel menu'*File*. Esso ti porterà a salvare un file `.ini` che potrai importare 
da linea di comando in questo modo:

    slic3r my_model.stl --load my_config.ini

Tu puoi sovrascrivere singole opzioni aggiungendole alla fine del comando come linea di comando:

    slic3r my_model.stl --load my_config.ini --fill-pattern concentric
Puoi anche creare un file di configurazione da linea di comando:

    slic3r --nozzle-diameter 0.35 --filament-diameter 2.85 \
        --temperature 185 --first-layer-temperature 195 --layer-height 0.2 \
        --save my_config.ini

Se sei un utente avanzato puoi suddividere le tue configurazioni in piu'
file *.ini* e caricarli aggiungendo più comandi di `--load`.

Uno o altri modi per usare le impostazioni base di stampa del filamento/stampa/stampante
da linea di comando è avviando Slic3r con l'opzione  `--autosave` :

    slic3r --autosave my_config.ini

Il comando sopra espresso avviera' l'interfaccia grafica di Slic3r but
esporterà automaticamente la configurazione corrente dello specifico file.
Quindi, l'ultima configurazione base verra' ricordata quando tu caricherai
quel file con il comando `--load` .

### Processare più file di input

Se tu fornisci piu' file di input a Slic3r, esso li processeraà separatamente
generando un distinto G-code per ogni file:

    slic3r model1.stl model2.stl model3.stl

Il comando di sopra generera' *model1.gcode*, *model2.gcode*,
*model3.gcode*.

Se tu vuoi processare più file come un singolo lavoro di stampa, tu puoi 
utilizzare l'opzione `--merge` (o `-m`):
    
    slic3r -m model1.stl model2.stl model3.stl

Questo genererà soltanto un nome file *model1.gcode* (ma tu puoi usare 
l'opzione `--output` descritta sopra per impostare un nome personalizzato) 
che contiene tutti e tre gli oggetti. Nopta che auto-arranging attualmente 
funziona al meglio quando tutti gli oggetti hanno dimensioni simili.

### Posizionare i file nelle coordinate G-code

I file di input (uno o più) verranno centrati attorno ad un punto di G-code definito
dell'opzione `--print-center`:

    slic3r my_model.stl --print-center 40,40

Di default, il punto di centro e' impostato a 100,100.

Riparando Modelli
----------------

Slic3r can be used to repair files from command line:

    slic3r --repair my_model.stl

This will generate a file named *my_model_fixed.obj* in the same directory
as the original one. This output filename is not customizable at the moment,
as well as the OBJ output format which is preferred over STL because it will
keep the model manifold by avoiding numerical issues frequently happening 
with STL. Note that Slic3r and most 3D applications are able to read OBJ files.

The `--info` switch can be used to get information about a file:

    slic3r --info cube.stl
    Info about cube.stl:
      size:              x=20.000 y=20.000 z=20.000
      number of facets:  12
      number of shells:  1
      volume:            8000
      needed repair:     no

Cutting models
--------------

Slic3r can be used to repair models from command line:

    slic3r --cut 10.2 my_model.stl

This will generate two files named *my_model_lower.stl* and *my_model_upper.stl*
in the same directory as the original model.

**Note:** the object will be automatically placed on the *z = 0* plane, so 
the argument for the `--cut` option is relative to the object's bottom, and
not to the original coordinate system.

Embedding Slic3r
----------------

The following options can be useful for embedding Slic3r into host applications:

* `--no-plater` will launch Slic3r in a configuration-only mode, thus avoiding
  confusion if the host application provides its own model loading dialog;
* `--autosave` will automatically export the last selected config to a specified
   file (see the above paragraph about [Configuration] for its usage);
* `--gui-mode` can take the `simple` or `expert` arguments, and will force Slic3r
  to launch in the specified mode.

