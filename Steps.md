# Installazione su Raspberry PI4 di FM Audit & 3CX :computer:
L'obiettivo finale sarà quello di creare un web server con Raspberry PI 4 ospitante 
FM Audit e o 3CX.<br>
<br>

[INSTALLAZIONE FISICA RASPBERRY PI4](#INSTALLAZIONE-FISICA-RASPBERRY-PI4)<br>
[INSTALLAZIONE FM AUDIT](#INSTALLAZIONE-RUFUS)<br>
[INSTALLAZIONE 3CX](#DOWNLOAD-SISTEMA-OPERATIVO)<br>


## INSTALLAZIONE FISICA RASPBERRY PI4
### tempo d'esecuzione: 15 min

Per l'installazione fisica del Raspberry PI 4 avremo bisogno di:
>            cacciavite a stella con punta piccola
>            pacchetto completo Raspberry Pi4 > 4GB RAM
>                  scheda madre completa
>                  alimentatore 15W circa (5.1V o 3.3V)
>                  ventola di raffreddamento e dissipatori (opzionale)
>                  case di protezione
>                  cavi di collegamento HDMI
>                  micro sd > 128GB con adattatore per PC
>            monitor
>            tastiera
>            cavo ethernet
>            software Balena Etcher installato sul PC

[MONTAGGIO COMPONENTI HARDWARE](#MONTAGGIO-COMPONENTI-HARDWARE)<br><br>
[SCARICARE IL FILE IMMAGINE DEL SISTEMA OPERATIVO](#SCARICARE-IL-FILE-IMMAGINE-DEL-SISTEMA-OPERATIVO)<br><br>
[DOWNLOAD SOFTWARE BALENA ETCHER](#DOWNLOAD-SOFTWARE-BALENA-ETCHER)<br><br>
[MONTARE IL SISTEMA OPERATIVO SU SCHEDA SD](#MONTARE-IL-SISTEMA-OPERATIVO-SU-SCHEDA-SD)<br><br>

# MONTAGGIO COMPONENTI HARDWARE
In base al pacchetto Raspberry comprato avremo diversi componenti da montare.
Montare i dissipatori di calore sui relativi SoC e chip. Fissare la scheda madre al case con le relative viti.
Attaccare sotto al case i gommini per evitare che le cariche elettrostatiche possano danneggiare i circuiti del Raspberry Pi 4.

# SCARICARE IL FILE IMMAGINE DEL SISTEMA OPERATIVO
[Scaricare il file immagine del S.O.](https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2021-05-28/2021-05-07-raspios-buster-armhf-lite.zip), studiato appositamente per Raspberry e basato su distro Debian, dal [sito ufficiale](https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2021-05-28/2021-05-07-raspios-buster-armhf-lite.zip). Verrà scaricata una cartella zip.

# DOWNLOAD SOFTWARE BALENA ETCHER
A questo punto sarà necessario scaricare il software [Balena Etcher](https://www.balena.io/etcher/), necessario per caricare il Sistema Operativo su micro SD, dal [sito ufficiale](https://www.balena.io/etcher/).

# MONTARE IL SISTEMA OPERATIVO SU SCHEDA SD
Una volta scaricato il Sistema Operativo sul PC e il programma Balena Etcher è il momento di caricare il Sistema Operativo su scheda SD.
Per prima cosa:
>       inserire la scheda SD con il relativo adattatore nello slot del PC


>       avviare il programma Balena Etcher
>       selezionare la voce "Flash from file"
>       selezionare il file immagine del sistema operativo (.zip)
>       selezionare la voce "Select target"
>       spuntare la casella con il nome 


### checkpoint :white_check_mark: <br>
Una volta assemblato saldamento e precisamente il tutto collegare il Raspberry 
alla rete elettrica con il relativo alimentatore e controllare che si accenda
correttamente (la ventola a 5.1V (pin 2 e 6) sarà discretamente rumorosa).Uno dei due led diverrà rosso a conferma che la scheda è correttamente alimentata. <br>

---------------------------------------------------------------------

