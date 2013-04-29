[<img src="https://raw.github.com/davidayalas/openelec-raspberry-pi/master/img/xbmc.jpg">](https://raw.github.com/davidayalas/openelec-raspberry-pi/master/img/xbmc.jpg)

Instal·lar la Raspberry PI com a centre multimèdia
===================================================

Aquest tutorial explica com convertir la Raspberry PI (Raspi) en un centre multimèdia mitjançant Openelec - XBMC (Open Embedded Linux Entertainment Center amb XBox Media Center). Hi ha altres distribucions de l'XBMC (Raspbmc o XBian). El procés d'instal·lació és diferent, però la configuració i els plugins disponibles són els mateixos.

Què necessitem?
---------------

* Tarja SD: amb 2GB n'hi ha prou però amb més grans no hi hauria d'haver problema. Per si de cas, consultar aquest enllaç [elinux.org/RPi_SD_cards](elinux.org/RPi_SD_cards)

* Descarregar l'última versió de l'Openelec per a Raspberry PI:

	* Linux: http://openelec.tv/get-openelec/download/viewcategory/10-raspberry-pi-builds
	* Mac: http://wiki.openelec.tv/index.php?title=Installing_OpenELEC_on_Raspberry_Pi#tab=Mac_OSX
	* Windows: http://squirrelhosting.co.uk/hosting-blog/hosting-blog-info.php?id=9

* Descarregar els següents plugins de vídeo en un pendrive:

	* Pelis a la carta: [http://blog.tvalacarta.info/plugin-xbmc/pelisalacarta/descargar/](http://blog.tvalacarta.info/plugin-xbmc/pelisalacarta/descargar/)
	* TV a la carta: [http://blog.tvalacarta.info/plugin-xbmc/tvalacarta/descargar/](http://blog.tvalacarta.info/plugin-xbmc/tvalacarta/descargar/)
	* Sports Devil: [https://code.google.com/p/xbmc-development-with-passion/wiki/SportsDevil](https://code.google.com/p/xbmc-development-with-passion/wiki/SportsDevil)
	* RtmpGUI+: [http://pluginsxbmc.blogspot.com.es/2013/01/rtmpgui-todo-el-futbol-en-xbmc.html](http://pluginsxbmc.blogspot.com.es/2013/01/rtmpgui-todo-el-futbol-en-xbmc.html)
	* Icefilms (repositori d'icefilms): [https://code.google.com/p/anarchintosh-projects/](https://code.google.com/p/anarchintosh-projects/)


Procés d'instal·lació
----------------------

* Seguir el procés d'instal·lació segons la plataforma: http://wiki.openelec.tv/index.php?title=Installing_OpenELEC_on_Raspberry_Pi

* Un cop instal·lat el sistema, posar la SD a la Raspi i arrencar-la

Setup inicial
--------------

* Per a la primera configuració serà necessari disposar d'un teclat connectat a un dels usb de la Raspi o bé una TV que permeti la utilització de la Raspi mitjançant el comandament a distància. O bé connectar per ssh a la raspberry des d'un altre equip i habilitar en els fitxers de configuració el control des d'altres dispositius.

* Anar a System > Setup. En aquest menú podem configurar totes les opcions d'XBMC:
	
	* Al menú "Aparença":

		- Internacional configurem la llengua i la regió horària

		- Skin > inhabilitem la opció de RSS (millorarà el rendiment ja que a la pantalla inicial no mostrarà notícies relacionades amb Openelec)

		- El temps > posen el "Weather Information" a cap / none (millorarà la càrrega inicial perquè no mostrarà el temps a la pantalla inicial)

	* Al menú "Serveis":

		- Habilitem "Airplay"

		- Habilitem "uPnP": permetrà enviar continguts a reproduir, com en airplay, però amb dispositiu Android, per exemple

		- Habilitar el Servidor web > permetre control per http: permetrà a aplicacions natives per Iphone o Android fer de comandament a distància de l'XBMC

		- Habilitar el Control Remot per a programes del propi XBMC i altres dispositius

	* Al menú "Complements" / "Add-ons":

		- Instal·lar des de zip (s'ha d'endollar el pendrive on hem descarregat els plugins de l'inici) > instal·lem un a un tots els plugins.
		El plugin d'Icefilms requereix instal·lar primer el repositori i després des de "Obtenir plugins", repositori "anarchintosh", addons de video, instal·lar icefilms

	* Al menú "Skin" > "Configuració" > "Pantalla principal" > Addons d'inici: es poden configurar els plugins que volem que siguin accessibles des de la pantalla principal. Des d'aquí podem configurar el addon per als subtítols, amb els idiomes preferits i els serveis que volem consultar per cercar subtítols.

Transmission
-------------

Si vols utilitzar la Raspi per descarregar continguts via torrent, pots instal·lar el [Transmission](http://en.wikipedia.org/wiki/Transmission_(BitTorrent_client\)) com a client de torrent.

Consta de dues parts:

* Servei transmission (el dimoni)
* Interfície de transmission

Anar a la pantalla de Sistema > Ajustos > Complements > Obtenir més complements:

* A Openelec addons anar a "Serveis" i instal·lar "Transmission": en el servei de transmission es pot configurar la carpeta on s'emmagatzemaran les descàrregues. Es pot seleccionar un disc extern (connectat per usb, per exemple). Reiniciar la Raspi.

* A Xbmc.org addons anar a "Addons d'aplicacions" i instal·lar "Transmission"

Es pot habilitar l'accés per HTTP de manera que es puguin desar els torrents sense haver d'entrar a la consola de la Raspi o bé es poden buscar torrents directament amb la interfície de programa que té el propi addon. Podem posar el Transmission a la pantalla principal de la mateixa manera que hem posat els plugins de vídeo. Anem a "Skin" > "Configuració" > "Pantalla principal" > Addons d'inici i posem el transmission com a addon a mostrar a la pantalla d'inici de "Programes"
