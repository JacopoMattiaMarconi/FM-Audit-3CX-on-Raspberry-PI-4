# Installazione su Raspberry PI4 di FM Audit & 3CX :computer:
L'obiettivo finale sarà quello di creare un web server con Raspberry PI 4 ospitante 
FM Audit e o 3CX.<br>
<br>

[INSTALLAZIONE FISICA RASPBERRY PI4](#INSTALLAZIONE-FISICA-RASPBERRY-PI4)<br><br>
[INSTALLAZIONE 3CX](#INSTALLAZIONE-3CX)<br><br>
[INSTALLAZIONE FM AUDIT](#INSTALLAZIONE-FM-AUDIT)<br>
<br><br><br><br><br><br>

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
[CONFIGURARE INTERFACCIA DI RETE](#CONFIGURARE-INTERFACCIA-DI-RETE)<br><br>
[COMANDI UTILI](#COMANDI-UTILI)<br><br>
<br><br><br>
# MONTAGGIO COMPONENTI HARDWARE
In base al pacchetto Raspberry comprato avremo diversi componenti da montare.
Montare i dissipatori di calore sui relativi SoC e chip. Fissare la scheda madre al case con le relative viti.
Attaccare sotto al case i gommini per evitare che le cariche elettrostatiche possano danneggiare i circuiti del Raspberry Pi 4.
NON collegare, per ora, il cavo di alimentazione alla reta elettrica.
<br><br><br>
# SCARICARE IL FILE IMMAGINE DEL SISTEMA OPERATIVO
[Scaricare il file immagine del S.O.](https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2021-05-28/2021-05-07-raspios-buster-armhf-lite.zip), studiato appositamente per Raspberry e basato su distro Debian, dal [sito ufficiale](https://downloads.raspberrypi.org/raspios_lite_armhf/images/raspios_lite_armhf-2021-05-28/2021-05-07-raspios-buster-armhf-lite.zip). Verrà scaricata una cartella zip.
<br><br><br>
# DOWNLOAD SOFTWARE BALENA ETCHER
A questo punto sarà necessario scaricare il software [Balena Etcher](https://www.balena.io/etcher/), necessario per caricare il Sistema Operativo su micro SD, dal [sito ufficiale](https://www.balena.io/etcher/).
<br><br><br>
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
<br><br><br>
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
<br><br><br>
# MONTARE LA SCHEDA SD SUL RASPBERRY
Una volta espulsa correttamente la scheda SD dal PC è il momento di inserirla, senza adattatore, nello slot del Raspberry PI4 ancora spento.
Inserita la scheda SD:
>         collegare il cavo ethernet tra Raspberry e porta ethernet a muro
>         collegare il cavo HDMI tra Raspberry e monitor collegato alla rete elettrica
>         collegare la tastiera al Raspberry
     
Infine:
>         collegare l'alimentatore tra Raspberry e presa elettrica
<br><br><br>
# CONFIGURARE IL SISTEMA OPERATIVO RASPBIAN
Attendere che il processo di avvio si completi e fare il login con l'utente predefinito "pi" e la password "raspberry".
Eseguire Raspbian con il comando: 
>         sudo raspi-config !ATTENZIONE: la tastiera sarà in inglese, il simbolo '-' si trova al posto del simbolo '''
D'ora in poi si dovrà premere il tasto <tab> e o <freccia su>/<freccia giù> per navigare tra le voci.
     
Attivare connessione SSH:
>         "Interface Options"
>         premere il tasto <invio>
>         "SSH" e tasto <invio>
>         selezionare "YES"
>         selezionare "OK"
     
### checkpoint :white_check_mark: <br>
D'ora in poi possiamo accedere all'interfaccia del Raspberry tramite "prompt dei comandi" di Windows, con il comando:
>         ssh <nome-utente>@<indirizzo-ip>
Ci verrà chiesto, poi, di inserire la password.
     
Cambiare impostazioni di codifica linguistica:
>         "Localisation Options"
>         premere il tasto <Invio>
>         "Locale" e tasto <invio>
>         <freccia in giù> 
>         deselezionare la voce "en..." evidenziata con '*' premendo il tasto <spazio>
>         selezionare la voce "it_IT.UTF-8 UTF-8" premendo il tasto <spazio>
>         premere il tasto <tab>
>         selezionare "OK"
>         selezionare la voce "it_IT.UTF-8 UTF-8"
>         premere il tasto <tab>
>         selezionare "OK"
 
Cambiare impostazioni di time zone:
>         "Localisation Options"
>         premere il tasto <invio>
>         "Timezone" e tasto <invio>
>         <freccia in giù> 
>         selezionare la voce "Europa" premendo il tasto <invio>
>         selezionare la voce "Roma" premendo il tasto <invio>

Cambiare impostazioni della tastiera:
>         "Localisation Options"
>         premere il tasto <Invio>
>         "Keyboard" e tasto <invio> 
>         selezionare la voce "Generic 105-key PC (intl.)" premendo il tasto <invio>
>         selezionare la voce "italiana" premendo il tasto <invio>
>         selezionare le voci predefinite e o le prime voci successive premendo il tasto <invio>

Cambiare impostazioni tecnologia WLAN:
>         "Localisation Options"
>         premere il tasto <Invio>
>         "WLAN Country" e tasto <invio> 
>         selezionare la voce "IT Italy" premendo il tasto <invio>
     
Aggiornare il Raspberry:
>         "Update"
>         premere il tasto <Invio>
<br><br><br>
# COMANDI UTILI
### Come muoversi tra le cartelle del Raspberry da linea di comando? :pushpin: <br>
>         cd /cartella/...

### Nel mondo linux non serve sapere a memoria il nome di una cartella, esiste l'autocompilazione (tasto <tab>) :pushpin: <br>
>         cd /car<tab>tella/...     


### Come editare un file su Raspberry da linea di comando? :pushpin: <br>
>         sudo nano file
oppure
>         sudo nano /cartella1/cartella2/file

### Come aggiornare il Raspberry da linea di comando? :pushpin: <br>
>         sudo apt-get update
>         sudo apt-get upgrade

### Come riavviare il Raspberry da linea di comando? :pushpin: <br>
>         sudo reboot
     
### Come spegnere il Raspberry da linea di comando? :pushpin: <br>
>         sudo shutdown -h now
     
### Come verificare le impostazioni di rete del Raspberry da linea di comando? :pushpin: <br>
>         ifconfig
oppure
>         ifconfig <nome-scheda-di-rete>
<br><br><br>
# CONFIGURARE INTERFACCIA DI RETE
>         sudo nano /etc/dhcpcd.conf
aggiungere le seguenti righe:
>         interface eth0
>            (3 spazi)static ip_address=<ip-statico-del-raspberry>
>            (3 spazi)static routers=<ip-del-router>
>            (3 spazi)static domain_name_servers=8.8.8.8

### checkpoint :white_check_mark: <br>
controllare che le impostazioni di rete siano state aggiunte correttamente
>         sudo reboot
>         ifconfig
<br><br><br>
---------------------------------------------------------------------
<br><br><br>
## INSTALLAZIONE 3CX
eseguire il seguente comando:
>         wget https://downloads-global.3cx.com/downloads/misc/d10pi.zip; sudo bash d10pi.zip 
una volta terminata l'installazione dei pacchetti seleziona:
>         1. 3CX
presta molta attenzione a scegliere il configuratore via web, selezionando:
>         1. Web Browser

### checkpoint :white_check_mark: <br>
A questo punto ti verrà assegnato un URL, che dovrai copiare e incollare sul tuo browser, per accedere all'interfaccia web del tuo 3CX.
L'URL avrà questo formato:
>         http://<indirizzo-ip>:5015
<br><br><br>    
---------------------------------------------------------------------
<br><br><br> 
## INSTALLAZIONE FM AUDIT
>         sudo apt install apt-transport-https dirmngr gnupg ca-certificates
>         sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
>         echo "deb https://download.mono-project.com/repo/debian stable-raspbianbuster main" | sudo tee /etc/apt/sources.list.d/mono-official-stable.list
>         sudo apt update
     
>         sudo apt install mono-devel
