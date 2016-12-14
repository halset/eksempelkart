# eksempelkart

## Oppgaver

### Oppgave 1 - komme i gang

* Klon eller fork+klon dette prosjektet slik at du får en kopi på egen harddisk.
* Åpne `index.html` (fra lokal disk) i Firefox og `style.json` i en teksteditor.
* Se på kartet og skumles filene.

### Oppgave 2 - stops

Bruk [Mapbox Style Specification](https://www.mapbox.com/mapbox-gl-style-spec/) og endre slik at dybdekurver (`DEPCNT`) slik at den blir litt tykkere når man zoomer inn. Hint: prøv med `stops`. Kan en diskret forskjell være bedre enn samme tykkelse hele veien?

### Oppgave 3 - roterte symboler med data-driven styling

Se på `S52_SYMBOL_135`. Den takler kun symboler rotert til 135 grader, men med [data-driven styling](https://www.mapbox.com/help/gl-dds-ref/) kan den endres til `S52_SYMBOL_ROTATE` og så heller bruke egenskapen `ROTATE` og dermed fungere for alle vinkler. Prøv det og se om det virker med `RCTLPT`-pilene vest for Mortavika-Arsvågen.

Prøv også å roter kartet og se hvor pilene peker. Det kan justeres med `icon-rotation-alignment`.

Roteringen stemmer ikke helt pga projeksjon. Det bør kanskje løses ved å introdusere en `ROTATE_CRS` som gjør om rotasjonsverdien fra storsirkel til skjerm for det aktuelle stedet og den aktuelle projeksjonen.

[Data-driven styling](https://www.mapbox.com/help/gl-dds-ref/) virker dessverre foreløpig kun på JS, men det er [ikke lenge til den også virker i Native på iOS og Android](https://github.com/mapbox/mapbox-gl-native/pull/7372).

### Oppgave 4 - Norge i Bilder

* Kopier `index.html` og `style.json` til nye filer og endre i html-filen så den peker på rett json.
* Legg til Norge i Bilder som en source. Bruk URLen `https://kartverket.maplytic.no/tile/_nib/{z}/{x}/{y}.jpeg` for automatisk håndtering av gatekeeper tokens.
* Legg til et layer for Norge i Bilder rett etter `background` med et innhold ala `{ "id": "nib", "type": "raster", "source": "nib" }`
* Fjern de gamle `landcover_*` og kanskje noen hus for å se Norge i Bilder.
* Sett fornuftig `maxzoom` for å unngå hvit skjerm når man zoomer for langt inn.

### Oppgave 5 - forbedre kartet

Finn ut hvordan kartene kan bli bedre og prøv å få det til. Bruk [Mapbox Style Specification](https://www.mapbox.com/mapbox-gl-style-spec/).
