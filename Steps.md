# Installazione su Raspberry PI4 di FM Audit & 3CX :computer:
L'obiettivo finale sarà quello di creare un sito raggiungibile da remoto e un disco di rete NAS.<br>
La configurazione iniziale del Raspberry verrà effettuata in maniera headless, tramite pc
portatile e connessione SSH.<br>
<br>

[INSTALLAZIONE FISICA RASPBERRY PI4](#INSTALLAZIONE-FISICA-RASPBERRY-PI4)<br>
[INSTALLAZIONE FM AUDIT](#INSTALLAZIONE-RUFUS)<br>
[INSTALLAZIONE 3CX](#DOWNLOAD-SISTEMA-OPERATIVO)<br>


## INSTALLAZIONE FISICA RASPBERRY PI4

Per l'installazione fisica del Raspberry PI 4 avremo bisogno di:
>            cacciavite a stella con punta piccola
>            pacchetto completo Raspberry Pi4 > 4GB RAM
>                  scheda madre completa
>                  alimentatore 15W circa (5.1V o 3.3V)
>                  ventola di raffreddamento e dissipatori (opzionale)
>                  case di protezione
>                  cavi di collegamento HDMI
>                  micro sd > 128GB con adattatore per PC
>            PC
>            cavo ethernet
>            software Balena Etcher installato sul PC

### tempo d'esecuzione: 15 min
Una volta acquistato il Raspberry Pi4 dovremo assemblare i componenti.
Le istruzioni contenute all'interno della scatola sono chiare e basilari. Qualora 
non fossero presenti si possono scaricare dal sito ufficiale.<br>

### checkpoint :white_check_mark: <br>
Una volta assemblato saldamento e precisamente il tutto collegare il Raspberry 
alla rete elettrica con il relativo alimentatore e controllare che si accenda
correttamente (la ventola a 5.1V (pin 2 e 6) sarà discretamente rumorosa).Uno dei due led diverrà rosso a conferma che la scheda è correttamente alimentata. <br>

---------------------------------------------------------------------

