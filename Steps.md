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
[MODIFICARE IL FILE CONFIG.TXT](#MODIFICARE-IL-FILE-CONFIG.TXT)<br><br>
[MONTARE LA SCHEDA SD SUL RASPBERRY](#MONTARE-LA-SCHEDA-SD-SUL-RASPBERRY)<br><br>
[CONFIGURARE IL SISTEMA OPERATIVO RASPBIAN](#CONFIGURARE-IL-SISTEMA-OPERATIVO-RASPBIAN)<br><br>

# MONTAGGIO COMPONENTI HARDWARE
In base al pacchetto Raspberry comprato avremo diversi componenti da montare.
Montare i dissipatori di calore sui relativi SoC e chip. Fissare la scheda madre al case con le relative viti.
Attaccare sotto al case i gommini per evitare che le cariche elettrostatiche possano danneggiare i circuiti del Raspberry Pi 4.
NON collegare, per ora, il cavo di alimentazione alla reta elettrica.

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
>       spuntare la casella con il nome della scheda SD
>       selezionare la voce "Flash!" e aspettare il termine del caricamento

### checkpoint :white_check_mark: <br>
Una volta terminato il caricamento la scheda SD non dovrebbe più vedersi dal PC.
Togliere la scheda SD dal PC e reinserirla nuovamente, in preparazione del prossimo passaggio.

# MODIFICARE IL FILE CONFIG.TXT
Una volta reinserita la scheda SD nello slot del PC:
>        selezionare la partizione "BOOT" in Esplora Risorse
>        aprire il file "config.txt"

Rimuovere '#' dalle seguenti linee:
>         hdmi_safe=1
>         hdmi_force_hotplug=1
>         hdmi_group=1
>         hdmi_mode=1
>         config_hdmi_boost=4

Salvare le modifiche effettuate, chiudere il file ed espellere la scheda SD in modo sicuro.


# MONTARE LA SCHEDA SD SUL RASPBERRY
Una volta espulsa correttamente la scheda SD dal PC è il momento di inserirla, senza adattatore, nello slot del Raspberry PI4 ancora spento.
Inserita la scheda SD:
>         collegare il cavo ethernet tra Raspberry e porta ethernet a muro
>         collegare il cavo HDMI tra Raspberry e monitor collegato alla rete elettrica
>         collegare la tastiera al Raspberry
     
Infine:
>         collegare l'alimentatore tra Raspberry e presa elettrica

# CONFIGURARE IL SISTEMA OPERATIVO RASPBIAN
Attendere che il processo di avvio si completi e fare il login con l'utente predefinito "pi" e la password "raspberry".
Eseguire Raspbian con il comando: 
>         sudo raspi-config
D'ora in poi si dovrà premere il tasto <tab> e o <freccia su>/<freccia giù> per navigare tra le voci.
     
Attivare connessione SSH:
>         "Interface Options"
>         premere il tasto <Invio>
>         "P2 SSH"
>         selezionare "YES"
>         selezionare "OK"
     
Attivare connessione SSH:
>         "Localisation Options"
>         premere il tasto <Invio>
>         "P2 SSH"
>         selezionare "YES"
>         selezionare "OK"
     

Selezionare "S4 Hostname", premere il tasto <Invio> e poi "OK" nella finestra di dialogo di avviso.
Inserire il nome host del Pi utilizzando solo caratteri alfanumerici e trattini ("-").
Selezionare <Fine> e poi <Si> per riavviare e applicare la configurazione del nome host.
---------------------------------------------------------------------

