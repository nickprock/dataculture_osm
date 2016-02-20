# Crea e condividi le tue mappe con TileMill #
(Pubblicato su [Startup Calabria](http://www.startupcalabria.com/crea-e-condividi-le-tue-mappe-con-tilemill/) il *20 Dicembre 2014*)

Ultimo appuntamento del 2014 con #DataCulture! Nella prima edizione abbiamo parlato di [come si diventa un OpenstreetMapper](http://www.startupcalabria.com/4-passi-per-diventare-un-openstreetmapper/), [la scorsa puntata era dedicata ad Osmose](http://www.startupcalabria.com/mappe-di-qualita-con-osmose/) un tool per correggere le mappe, oggi finalmente si parlerà di come riutilizzare i dati e costruire le nostre mappe.

Oggi creeremo una **mappa interattiva dei dati ISTAT sulla produzione di rifiuti e il riciclaggio nelle città copoluogo di provincia**.

Il tool che useremo oggi è [TileMill](https://www.mapbox.com/tilemill/), un'**applicazione open source** rilasciata da [Mapbox](https://www.mapbox.com/), una delle società che fanno business sui dati OSM e principale concorrente di Google.

Mapbox è un servizio freemium che permette di personalizzare le mappe che poi andranno sui nostri portali o verranno condivise sui social network, [con dei piani basati su memoria utlizzata e view](https://www.mapbox.com/pricing/). Per prima cosa, per rendere più semplice il tutorial, ho aperto un account free sul sito così da poter condividere nel modo più semplice possibile la mappa creata.

Una volta entrati nell'account vediamo che c'è un editor on-line per i progetti che non è ciò che useremo oggi. Passiamo, quindi, al core dell'articolo e scarichiamo **TileMill** (oggi si lavora off-line!), è **free platform** quindi scaricate la versione che vi serve (io lavoro su Ubuntu 32-bit) e seguite il [wiki di installazione](https://www.mapbox.com/tilemill/docs/linux-install/), è tutto molto semplice.

Installato, apriamo e ci appare la schermata con i progetti, ne esistono alcuni di default, come potete vedere nella mia c'è un *"Primo Test"* che si riferisce a un [tutorial ufficiale](https://www.mapbox.com/tilemill/docs/crashcourse/point-data/), e quello di questo tutorial.

![tilemill1](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-1.png)
