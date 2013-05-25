[<img src="https://raw.github.com/davidayalas/openelec-raspberry-pi/master/img/xbmc.jpg">](https://raw.github.com/davidayalas/openelec-raspberry-pi/master/img/xbmc.jpg) [<img src="https://raw.github.com/davidayalas/openelec-raspberry-pi/master/img/raspi.jpg">](https://raw.github.com/davidayalas/openelec-raspberry-pi/master/img/raspi.jpg)

Instal·lar la Raspberry PI com a centre multimèdia
===================================================

Aquest tutorial explica com convertir la Raspberry PI (Raspi) en un centre multimèdia mitjançant Openelec - XBMC (Open Embedded Linux Entertainment Center amb XBox Media Center). Hi ha altres distribucions de l'XBMC (Raspbmc o XBian). El procés d'instal·lació és diferent, però la configuració i els plugins disponibles són els mateixos (excepte aquelles configuracions que es facin des dels menús o plugins propis d'Openelec, com pot ser la instal·lació del transmission o la configuració d'IP fixa).

Què necessitem?
---------------

* Tarja SD: amb 2GB n'hi ha prou però amb més grans no hi hauria d'haver problema. Per si de cas, consultar aquest enllaç [elinux.org/RPi_SD_cards](elinux.org/RPi_SD_cards)

* Descarregar l'última versió de l'Openelec per a Raspberry PI:

	* Linux: http://openelec.tv/get-openelec/download/viewcategory/10-raspberry-pi-builds
	* Mac: http://wiki.openelec.tv/index.php?title=Installing_OpenELEC_on_Raspberry_Pi#tab=Mac_OSX
	* Windows: http://squirrelhosting.co.uk/hosting-blog/hosting-blog-info.php?id=9 <br>

* Descarregar els següents plugins de vídeo en un pendrive:

	* Pelis a la carta: http://blog.tvalacarta.info/plugin-xbmc/pelisalacarta/descargar/
	* TV a la carta: http://blog.tvalacarta.info/plugin-xbmc/tvalacarta/descargar/
	* Sports Devil: https://code.google.com/p/xbmc-development-with-passion/wiki/SportsDevil
	* RtmpGUI+: http://pluginsxbmc.blogspot.com.es/2013/01/rtmpgui-todo-el-futbol-en-xbmc.html
	* Icefilms (repositori d'icefilms): https://code.google.com/p/anarchintosh-projects/


Procés d'instal·lació
----------------------

* Seguir el procés d'instal·lació segons la plataforma: http://wiki.openelec.tv/index.php?title=Installing_OpenELEC_on_Raspberry_Pi

* Un cop instal·lat el sistema, posar la SD a la Raspi i arrencar-la

Setup inicial
--------------

* Per a la primera configuració serà necessari disposar d'un teclat connectat a un dels usb de la Raspi o bé una TV que permeti la utilització de la Raspi mitjançant el comandament a distància (la TV ha d'implementar l'estàndard [CEC](http://wiki.xbmc.org/index.php?title=CEC)). O bé connectar per ssh a la raspberry des d'un altre equip i habilitar en els fitxers de configuració el control des d'altres dispositius.

* Anar a System > Setup. En aquest menú podem configurar totes les opcions d'XBMC:
	
	* Al menú "Aparença":

		- Internacional configurem la llengua i la regió horària

		- Skin > inhabilitem la opció de RSS (millorarà el rendiment ja que a la pantalla inicial no mostrarà notícies relacionades amb Openelec)

		- El temps > posen el "Weather Information" a cap / none (millorarà la càrrega inicial perquè no mostrarà el temps a la pantalla inicial) <br />  

	* Al menú "Serveis":

		- Habilitem "Airplay"

		- Habilitem "uPnP": permetrà enviar continguts a reproduir, com en airplay, però amb dispositiu Android, per exemple

		- Habilitar el Servidor web > permetre control per http: permetrà a aplicacions natives per Iphone o Android fer de comandament a distància de l'XBMC

		- Habilitar el Control Remot per a programes del propi XBMC i altres dispositius <br />  

	* Al menú "Complements" / "Add-ons":

		- Instal·lar des de zip (s'ha d'endollar el pendrive on hem descarregat els plugins de l'inici) > instal·lem un a un tots els plugins.
		El plugin d'Icefilms requereix instal·lar primer el repositori i després des de "Obtenir plugins", repositori "anarchintosh", addons de video, instal·lar icefilms <br />  

	* Al menú "Skin" > "Configuració" > "Pantalla principal" > Addons d'inici: es poden configurar els plugins que volem que siguin accessibles des de la pantalla principal. Des d'aquí podem configurar el addon per als subtítols, amb els idiomes preferits i els serveis que volem consultar per cercar subtítols.

* Anar Sistema > Openelec. Configurarem el sistema per a que s'actualitzi automàticament. D'aquesta manera tindrem disponible l'última versió de XBMC un cop s'alliberi una nova versió de Openelec.  <br /> 


Transmission
-------------

Si vols utilitzar la Raspi per descarregar continguts via torrent, pots instal·lar el [Transmission](http://en.wikipedia.org/wiki/Transmission_(BitTorrent_client\)) com a client de torrent.

Consta de dues parts:

* Servei transmission (el dimoni)
* Interfície de transmission

Anar a la pantalla de Sistema > Configuració > Complements > Obtenir més complements:

* A Openelec addons anar a "Serveis" i instal·lar "Transmission": en el servei de transmission es pot configurar la carpeta on s'emmagatzemaran les descàrregues. Es pot seleccionar un disc extern (connectat per usb, per exemple). Reiniciar la Raspi.

* A Xbmc.org addons anar a "Addons d'aplicacions" i instal·lar "Transmission"

Es pot habilitar l'accés per HTTP de manera que es puguin desar els torrents sense haver d'entrar a la consola de la Raspi o bé es poden buscar torrents directament amb la interfície de programa que té el propi addon. Podem posar el Transmission a la pantalla principal de la mateixa manera que hem posat els plugins de vídeo. Anem a "Skin" > "Configuració" > "Pantalla principal" > Addons d'inici i posem el transmission com a addon a mostrar a la pantalla d'inici de "Programes"

Configurar IP fixa
-------------------

Anar a "Sistema" a la pantalla principal i a l'opció que es desplega a sota, seleccionar Openelec.

A la pantalla que s'obre anar al menú "Xarxa" i anar a l'opció "Adreça ip".

S'ha de posar una ip del teu rang, la màscara de xarxa, el gateway i el dns (normalment aquestes dues últimes opcions seran 192.168.1.1 o 192.168.0.1)

Configurar WIFI
-------------------

La raspberry és compatible amb dispositius WIFI usb. Per configurar l'accés s'ha d'anar a "Sistema" des de la pantalla principal i a l'opció que es desplega a sota, seleccionar Openelec. Un cop aquí, a xarxa, es pot seleccionar l'interfície de xarxa a utilitzar (eth=ethernet, wlan=wifi lan). Si seleccionem aquesta segona opció, podrem introduir l'SSID de la nostra xarxa, el tipus de seguretat i la contrasenya.

Control de XBMC des del mòbil
------------------------------

Anar al market del teu terminal i cercar "xbmc remote". Segons el sistema operatiu, el control remot incorporarà una opció per autodescobriment a la xarxa de sistemes XBMC (el telèfon ha d'estar connectat mitjançant WIFI a la mateixa xarxa). En cas que no sigui així i no puguis obtenir la ip de l'XBMC, hauràs d'entrar al router i mirar els dispositius connectats en aquell moment per obtenir-la.


Reproducció de continguts via AirPlay o uPnP (Android, altres)
-------------------------------------------------------

Amb dispositius iOS ja està integrat en les aplicacions que poden reproduir continguts en altres dispositius.

Per a dispositius Android existeixen diverses aplicacions, per exemple, "iMediaShare"