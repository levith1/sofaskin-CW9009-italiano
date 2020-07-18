# Sofaskin-CW9009
Modifiche CW9009 al codice alle pagine web Sofaskin per WeeWx originariamente sviluppato da Sven su http://neopround.com/project/weewx. Per favore guarda il readme per i requisiti per usare questo skin. Una versione italiana di queste pagine è disponibile su  http://micae.it/2017/12/28/sofaskin-italiano/.

Sofaskin V1.1 è sviluppato da Sven su Neoground: https://neoground.com/portfolio/neowx/. ***Sven da tempo non supporta lo skin originale.*** Questo è un grande template ma ho apportato delle modifiche secondo le mie necessità. Ho anche aggiunto del codice da altri template <a href="http://www.dajda.net">dajda.net</a> per le tabelle storiche NOAA. C'è anche del codice aggiunto da <a href=http://www.torkel.se/weather/index.html> Björn Torkelsson</a>. Una lista dei cambiamenti è elencate sotto con le istruzioni per impostare le tabelle. 

- Aggiunte delle variabili nel file skin.conf per la personalizzazione delle pagine. 
- Rimosse le tabelle mensili e annuali dalla lista drop down list e aggiunte in una pagina separata. 
- Usata una tabella record di sempre.
- Aggiunta una pagina stazione per le informazioni di chi gestisce il sito.  
- Aggiunto un bottone Menu per gli schermi piccoli.
- Refresh automatico della pagina ogni dieci minuti.
- Aggiunto il codice da dajda.net che produce le tabelle storiche.Lo script historygenerator.py deve essere aggiunto a WeeWx per funzionare.
- Creata una pagina PHP al template per vedere i testi NOAA.
- Aggiunto un allarme se  i dati meteo sono vecchi (più di 30 minuti). (Scritto da Björn Torkelsson) 
- Impostato un codice javascript nella sezione web cam nella sezione di index.html con uno slideshow CSS per abilitare  più di due web cam.
- Nella traduzione italiana ho notato che cambiando alcune cose tipo fasi lunari o titoli dei grafici nel file skin.conf comunque non funziona, ho risolto facendo gli stessi cambiamenti nel file weewx.conf.

<b>Responsive Menu:</b><br>
Ho aggiunto un migliore menu responsive che usa meno spazio verticale per gli screen più piccoli.

![screenshot_20161127-062548](https://cloud.githubusercontent.com/assets/22601363/20864991/f2f14eb8-b9c2-11e6-8bba-b4043f425bbb.png)
![screenshot_20161201-124209](https://cloud.githubusercontent.com/assets/22601363/20864992/f4b96654-b9c2-11e6-8346-650fee6db484.png)
<br><br>
<b>History Table:</b><br>
Lo script historygenerator.py era una parte del template sviluppato da http://www.dajda.net/index.html. Altre informazioni sul template sono disponibili su http://www.dajda.net/about.html ed il template originale è disponibile su GitHub
https://github.com/brewster76/fuzzy-archer. Ho modificato il codice in historygenerator.py per creare il giusto link html nella tabella storica NOAA e scritto una pagina php per vedere le tabelle. 

![template](https://cloud.githubusercontent.com/assets/22601363/20864962/3f40b91c-b9c2-11e6-8298-75bec529dc40.jpg)
<br><br>
<b>Allarme dati vecchi:</b><br>
Mostra un messaggio di alert quando i dati sono vecchi di X minuti. Il termine di default è di 30 minuti ma può essere modificato nel file checkdiff.js della cartella js. 

![olddata](https://cloud.githubusercontent.com/assets/22601363/21075763/496c385c-bed7-11e6-82e8-789ffa300601.jpg)
<br><br>
<b>Istruzioni di Installazione:</b><br>
Installare il template è come per gli altri skins. Hai bisogno di mettere i file dello skin nella cartella /etc/weewx/skins. Hai anche bisogno di cambiare le variabili skin nel file weewx.conf sotto Standard Reports. 

Example:<br>
[[StandardReport]]
skin = Sofaskin 

Devi anche mettere lo script python historygenerator.py nella directory /usr/share/weewx/user. Il file skin.conf ha già il codice per usare le tabelle così non devi fare altro a meno che non voglia cambiare i colori. Altre informazioni su historygenerator.py e come di usano le tabelle sono disponibili ai link di seguito.
https://github.com/brewster76/fuzzy-archer/blob/master/INSTALL

<b>IMPORTANTE:</b>
Devi aggiornare le variabili nella sezione EXTRA del file skin.conf per le informazioni della tua stazione. Come ad esempio:

```
[Extras]
    # Template Extras
 
    # Website URL
    #web_url = 

    # radar
    #radar = '<iframe class="iframe" src="https://embed.windy.com/embed2.html?lat=43.555&lon=-116.348&zoom=9&level=surface&overlay=radar&menu=&message=&marker=&calendar=&pressure=&type=map&location=coordinates&detail=&detailLat=43.555&detailLon=-116.348&metricWind=default&metricTemp=default&radarRange=-1"></iframe>'

    # Lightning map and hyperlink
    #lightning_map = http://images.lightningmaps.org/blitzortung/america/index.php?map=usa&period=0.25
    #lightning_url = http://www.lightningmaps.org/realtime 

    # You. Only shows up in footer
    #you = 
    #emailname = 
    #email =  
   
    # Camera link
    # camera and cameratitle are arrays of the camera links and camera names. 
    #cameratitle = "Hwy 69 - Amity", "Victory - Five Mile", "Reflection Ridge", "Bridgeview South"
    #camera = http://www.achdidaho.org/ATIS/CCTV/CCTV_588.jpg, http://www.achdidaho.org/ATIS/CCTV/CCTV_649.jpg, https://icons.wunderground.com/webcamramdisk/l/a/lakearrowheadnw/3/current.jpg?1535944393, https://icons.wunderground.com/webcamramdisk/m/i/miralem77/4/current.jpg?1536106630  
    
    # Google Analytics ID
    #googleAnalyticsId = 

    #CWOP
    #cwop = 
    #cwop_url = 
```
Se hai problemi mi puoi inviare una email a josh@cw9009.x10host.com oppure info@meteopaupisi.it per la traduzione in italiano.  
