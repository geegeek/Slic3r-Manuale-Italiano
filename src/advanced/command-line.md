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

**Nota:** the print/filament/printer presets defined in the graphical interface
are completely ignored when running in command line mode. Slic3r will always
default to its factory default settings.

You'll need to export your desired configuration with the *Export Config...*
command, which is located in the *File* menu. It will prompt you to save a
`.ini` file that you can load from command line this way:

    slic3r my_model.stl --load my_config.ini

You can override single options by appending them as command line switches:

    slic3r my_model.stl --load my_config.ini --fill-pattern concentric

You can also create a config file from command line:

    slic3r --nozzle-diameter 0.35 --filament-diameter 2.85 \
        --temperature 185 --first-layer-temperature 195 --layer-height 0.2 \
        --save my_config.ini

If you're an advanced user you can split your configuration into multiple 
*.ini* files and load them by appending multiple `--load` switches.

One more way to use the print/filament/printer presets on command line is
launching Slic3r with the `--autosave` option:

    slic3r --autosave my_config.ini

The above command will launch the graphical interface of Slic3r but will
automatically export the current configuration to the specified file. Thus,
the last used presets will be remembered whenever you `--load` that file.

### Processing multiple input files

If you supply multiple input files Slic3r will process them separately, 
by generating a distinct G-code file for each one:

    slic3r model1.stl model2.stl model3.stl

The command above will generate *model1.gcode*, *model2.gcode*,
*model3.gcode*.

If you want to process multiple files as a single print job, you can use
the `--merge` (or `-m`) option:
    
    slic3r -m model1.stl model2.stl model3.stl

This will only generate a file named *model1.gcode* (but you can use the 
`--output` option described above to set a custom name) containing all three
objects. Note that auto-arranging currently works best when all objects have
similar sizes.

### Positioning files in the G-code coordinates

Input file(s) will be centered around the G-code point defined by the
`--print-center` option:

    slic3r my_model.stl --print-center 40,40

By default, the center point is set to 100,100.

Repairing models
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

