.. note::

    Ciao, benvenuto nella community di SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts su Facebook! Approfondisci le tue conoscenze su Raspberry Pi, Arduino ed ESP32 insieme ad altri appassionati.

    **Perché unirti a noi?**

    - **Supporto esperto**: Risolvi i problemi post-vendita e le sfide tecniche con l'aiuto della nostra community e del nostro team.
    - **Impara e condividi**: Scambia suggerimenti e tutorial per migliorare le tue competenze.
    - **Anteprime esclusive**: Ottieni accesso anticipato agli annunci di nuovi prodotti e anteprime.
    - **Sconti speciali**: Goditi sconti esclusivi sui nostri nuovi prodotti.
    - **Promozioni festive e giveaway**: Partecipa a promozioni festive e concorsi a premi.

    👉 Pronto a esplorare e creare con noi? Clicca [|link_sf_facebook|] e unisciti oggi stesso!

FAQ
==============

Come cambiare il canale Wi-Fi
----------------------------------

La banda Wi-Fi a 2,4GHz dispone di canali che vanno da 1 a 13. ESP32 supporta i canali da 1 a 11. Altri dispositivi che operano sullo stesso canale possono causare interferenze, portando a problemi di connessione. Per mitigare questo problema, puoi provare a cambiare canale. Per impostazione predefinita, il canale è impostato su 1. Quando selezioni un nuovo canale, si consiglia di saltare 1-2 canali alla volta. Ad esempio, se il canale attuale è 1, prova prima con il canale 3 e, se il segnale è ancora debole, passa al canale 5.

.. note::

   È necessaria la versione 1.4.1 o superiore del firmware ESP32 CAM per cambiare canale. Consulta :ref:`update_firmware` per ulteriori dettagli.

#. Accendi il GalaxyRVR. Per attivare l'ESP32 CAM, sposta l'interruttore di modalità sulla posizione **Run** e premi il pulsante **reset** per riavviare la scheda R3.

     .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/play_reset.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

#. Trova ``GalaxyRVR`` nell'elenco delle reti disponibili sul tuo dispositivo mobile (tablet o smartphone), inserisci la password ``12345678`` e connettiti.

     .. note::

        * La connessione attuale è all'hotspot GalaxyRVR, quindi non c'è accesso a Internet. Se richiesto di cambiare rete, scegli "Rimani connesso".

     .. image:: img/app/camera_lan.png
        :width: 500

#. Apri un browser web sul tuo dispositivo mobile e vai su ``http://192.168.4.1`` per accedere alla pagina di aggiornamento OTA di ESP32 CAM.

   .. image:: img/faq_cam_ota_141.jpg
      :width: 400

#. Nella sezione **Wi-Fi AP Channel**, seleziona un canale diverso.

   * Il canale predefinito è il 1. Quando selezioni un nuovo canale, salta 1-2 canali alla volta (ad esempio, dal canale 1 al 3, e se necessario, al 5).  
   * Fai clic sul pulsante **Confirm** per salvare le modifiche.

   .. image:: img/faq_cam_ota_channel.png
      :width: 400

#. Verrà visualizzato un popup di conferma che ti chiederà di riavviare il dispositivo. Fai clic su **Confirm**.

   .. image:: img/faq_cam_ota_reset.jpg
      :width: 400
   
#. Premi il pulsante **Reset** per riavviare il dispositivo. Il GalaxyRVR è ora pronto per il normale funzionamento.

   .. image:: img/camera_reset.png

.. _update_firmware:

Come aggiornare il firmware di ESP32 CAM
-----------------------------------------

Segui questi passaggi dettagliati per aggiornare il firmware del tuo ESP32 CAM:

#. Accendi il GalaxyRVR. Per attivare l'ESP32 CAM, sposta l'interruttore di modalità sulla posizione **Run** e premi il pulsante **reset** per riavviare la scheda R3.

     .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/play_reset.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

#. Trova ``GalaxyRVR`` nell'elenco delle reti disponibili sul tuo dispositivo mobile (tablet o smartphone), inserisci la password ``12345678`` e connettiti.

     .. note::

        * La connessione attuale è all'hotspot GalaxyRVR, quindi non c'è accesso a Internet. Se richiesto di cambiare rete, scegli "Rimani connesso".

     .. image:: img/app/camera_lan.png
        :width: 500

#. Fai clic sul link sottostante per scaricare il file del firmware ``ai-camera-firmware-v1.4.1-ota.bin`` e salvalo sul tuo dispositivo mobile.

   * :download:`File del firmware di ESP32 CAM <https://github.com/sunfounder/ai-camera-firmware/releases/download/1.4.1/ai-camera-firmware-v1.4.1-ota.bin>`

#. Apri un browser web sul tuo dispositivo mobile e vai su ``http://192.168.4.1`` per accedere alla pagina di aggiornamento OTA di ESP32 CAM.

   .. image:: img/faq_cam_ota.jpg
      :width: 400

#. Nella pagina OTA, fai clic sul pulsante per selezionare il file del firmware.

   .. image:: img/faq_cam_ota_choose.png
      :width: 400

#. Scegli il file ``ai-camera-firmware-v1.4.1-ota.bin`` precedentemente scaricato dal tuo dispositivo e fai clic su **OK**.

   .. image:: img/faq_cam_ota_file.png
      :width: 400

#. Fai clic sul pulsante **Update** per avviare il processo di aggiornamento del firmware.

   .. image:: img/faq_cam_ota_update.png
      :width: 400
   
#. Attendi il completamento dell'aggiornamento. Una volta che il numero di versione visualizzato passa a ``1.4.1``, l'aggiornamento è stato completato con successo.

   .. image:: img/faq_cam_ota_finish.png
      :width: 400
   
#. Dopo il completamento dell'aggiornamento, puoi chiudere il browser web. Premi il pulsante **Reset** per riavviare il dispositivo. L'ESP32 CAM è ora pronto per il normale funzionamento.

   .. image:: img/camera_reset.png

.. _upload_galaxy_code:

Come caricare il codice ``galaxy-rvr.ino``?
-----------------------------------------------

Di default, la scheda Uno R3 del GalaxyRVR è preinstallata con il firmware necessario, permettendoti di controllarlo tramite l'APP. Se il tuo R3 è stato sovrascritto con altro codice ma desideri tornare al firmware predefinito e continuare con il processo :ref:`quick_start`, segui questi passaggi per ricaricare il codice sulla scheda R3:

#. Usa un cavo USB per collegare l'Arduino al computer. Successivamente, posiziona l'interruttore **upload** sul rover in posizione "upload".

   .. image:: img/camera_upload.png
        :width: 400
        :align: center

#. Scarica il firmware necessario dal link qui sotto: 
        
   * :download:`File del firmware della scheda R3 <https://github.com/sunfounder/galaxy-rvr/releases/download/1.1.0/galaxy-rvr-1.1.0.zip>`

#. Estrai il file zip scaricato, quindi fai doppio clic sul file ``update-arduino-firmware.bat`` per eseguirlo.

   .. image:: img/faq_firmware_file.png

#. Digita il numero corrispondente alla scheda Arduino Uno del tuo GalaxyRVR (es. ``2``) e premi **Invio** per avviare l'aggiornamento.

   .. note::

     * Se la porta COM corretta non appare, o se non sei sicuro di quale sia, disconnetti altri dispositivi USB dal computer, lasciando connesso solo il rover.  
     * Se incontri un errore come "avrdude.exe: stk500_getsync() attempt 1 of 10: not in sync: resp=0xXX", assicurati che l'interruttore **upload** sul rover sia impostato sulla posizione "upload", come descritto nel passaggio 1.

   .. image:: img/faq_firmware_port.png
      :width: 600

#. Dopo poco tempo, il nuovo codice verrà caricato correttamente sulla scheda Uno R3 del GalaxyRVR.

   .. image:: img/faq_firmware_finish.png
      :width: 600

.. _ap_to_sta:

Configurazione della rete del Rover: WiFi domestico e modalità AP  
---------------------------------------------------------------------------------------------------------------

Per impostazione predefinita, l'Uno R3 è precaricato con un codice configurato in **modalità AP**. Ciò significa che il **GalaxyRVR** trasmetterà un hotspot, consentendoti di connettere il tuo dispositivo mobile e controllarlo tramite l'**app SunFounder Controller**.

Se preferisci controllare il rover tramite la tua rete WiFi domestica o hai bisogno di **reimpostare la modalità AP** per evitare conflitti di nome tra più dispositivi, segui questi passaggi per caricare il codice modificato sulla scheda Uno:

#. Scarica i file richiesti dal seguente link:

   * :download:`Codici GalaxyRVR <https://github.com/sunfounder/galaxy-rvr/archive/refs/heads/main.zip>`

#. Consulta la guida all'installazione: :ref:`install_arduino_ide`.

#. Usa il **Gestore Librerie** per installare le librerie ``SoftPWM`` e ``SunFounder AI Camera``. Per istruzioni dettagliate, consulta :ref:`install_lib`.

#. Vai alla cartella ``galaxy-rvr-main\galaxy-rvr`` e apri il file ``galaxy-rvr.ino``.

   .. image:: img/faq_galaxy_code.png

#. Commenta le righe 69-71, rimuovi i commenti dalle righe 73-75 e sostituisci ``SSID`` e ``PASSWORD`` con le credenziali della tua rete WiFi domestica.

   .. code-block:: c

      // /** Configurazione modalità WiFi, SSID, password */
      // #define WIFI_MODE WIFI_MODE_AP
      // #define SSID "GalaxyRVR"
      // #define PASSWORD "12345678"

      #define WIFI_MODE WIFI_MODE_STA
      #define SSID "xxxxxxxxxx"
      #define PASSWORD "xxxxxxxxxx"

#. Collega il **GalaxyRVR** al computer con un cavo **USB** e sposta l'interruttore **upload** del rover sulla posizione di caricamento.

   .. image:: img/camera_upload.png
        :width: 400
        :align: center

#. Fai clic sul pulsante **Upload** nell'IDE di Arduino per caricare il codice modificato sulla scheda Uno.

   .. image:: img/faq_galaxy_upload.png

#. Per attivare **ESP32 CAM**, sposta l'interruttore della modalità su **Run**, quindi premi il pulsante **reset** per riavviare la scheda R3. Noterai una luce **ciano lampeggiante** sulla striscia LED inferiore.

   .. raw:: html
   
       <video width="600" loop autoplay muted>
           <source src="_static/video/play_reset.mp4" type="video/mp4">
           Your browser does not support the video tag.
       </video>

#. Assicurati che il tuo dispositivo mobile (tablet o smartphone) sia connesso alla tua rete **WiFi domestica**.

   .. image:: img/faq_connect_wifi.jpg
        :width: 400
        :align: center

#. Apri l'**app SunFounder Controller**, tocca l'icona "+", crea un nuovo controller, seleziona il **preset "GalaxyRVR"**, inserisci un nome oppure tocca **"Conferma"** per continuare.

   .. image:: img/app/play_preset.jpg
        :width: 600

#. L'app cercherà automaticamente il **GalaxyRVR**. Dopo qualche istante, apparirà un messaggio con scritto **"Connessione riuscita"**.

   .. image:: img/app/auto_connect.jpg
        :width: 600
    
#. Ora, tocca il pulsante **|app_run|** per visualizzare lo **stream video in tempo reale** della telecamera e controllare il rover utilizzando i widget disponibili.

   .. image:: img/app/play_run_view.jpg
        :width: 600 


**Reimpostazione della modalità AP**  

#. Per reimpostare la modalità **AP** e modificare **SSID** e **password**, assicurati che le righe relative alla modalità AP siano abilitate e aggiorna i valori di **SSID** e **password**.

   .. code-block:: c

      #define WIFI_MODE WIFI_MODE_AP 
      #define SSID "newSSIDName" 
      #define PASSWORD "newPassword"

      // #define WIFI_MODE WIFI_MODE_STA
      // #define SSID "xxxxxxxxxx"
      // #define PASSWORD "xxxxxxxxxx"

#. Segui gli stessi **passaggi per il caricamento del codice** descritti sopra.

#. Dopo il caricamento, il **GalaxyRVR** trasmetterà la sua **rete personalizzata** con il nuovo nome e la nuova password, consentendo una **connessione diretta** senza dover utilizzare una rete WiFi domestica.


    
Come invertire la fotocamera?  
----------------------------------------

Se trovi il feed della fotocamera capovolto mentre usi il SunFounder Controller, puoi correggerlo facilmente tramite l'app. Segui questi passaggi:  

1. Tocca il pulsante |app_edit| in alto a destra.  

   .. image:: img/app/faq_edit.png  
        :width: 500 

2. Clicca il pulsante **camera** per aprire un popup. Attiva l'interruttore **Inverted** per abilitarlo.  

   .. image:: img/app/faq_inverted.png  
        :width: 500  

3. Salva le impostazioni.  

   .. image:: img/app/faq_save.png  
        :width: 500 

4. Torna all'interfaccia di controllo e clicca il pulsante |app_run|.  

   .. note::  

        Occasionalmente, il feed della fotocamera potrebbe non apparire. In questo caso, metti in pausa il controller e poi clicca nuovamente il pulsante di esecuzione.  

   .. image:: img/app/faq_run.png  
        :width: 500 
    
.. _install_lib:

Errore di compilazione: ``SoftPWM.h`` o ``SunFounder_AI_Camera.h``: File o directory non trovato?
------------------------------------------------------------------------------------------------------------

Se ricevi un messaggio di errore "Errore di compilazione: ``SoftPWM.h``: File o directory non trovato", significa che non hai installato la libreria SoftPWM.

Installa le due librerie necessarie ``SoftPWM`` e ``SunFounder AI Camera`` come mostrato.

    .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/install_softpwm.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

Per la libreria ``SunFounder AI Camera``, devi selezionare "INSTALLA TUTTO" per installare contemporaneamente la dipendenza ``ArduinoJson`` richiesta.

   .. image:: img/faq_install_ai_camera.png
      :width: 600


avrdude: stk500_getsync() tentativo 10 di 10: non in sincronia: resp=0x6e?
---------------------------------------------------------------------------------
Se compare il seguente messaggio dopo aver cliccato il pulsante **Upload**, anche se la scheda e la porta sono state selezionate correttamente:

.. code-block::

    avrdude: stk500_recv(): programmer is not responding
    avrdude: stk500_getsync() attempt 1 of 10: not in sync: resp=0x00
    avrdude: stk500_recv(): programmer is not responding
    avrdude: stk500_getsync() attempt 2 of 10: not in sync: resp=0x00
    avrdude: stk500_recv(): programmer is not responding
    avrdude: stk500_getsync() attempt 3 of 10: not in sync: resp=0x00
    At this point, you need to make sure that the ESP32 CAM is unplugged.

L'ESP32-CAM e la scheda Arduino condividono gli stessi pin RX (ricezione) e TX (trasmissione). Pertanto, prima di caricare il codice, dovrai scollegare l'ESP32-CAM per evitare conflitti o potenziali problemi.

    .. image:: img/camera_upload.png
        :width: 500
        :align: center

Dopo aver caricato correttamente il codice, se hai bisogno di utilizzare l'ESP32 CAM, sposta l'interruttore a sinistra per avviare l'ESP32 CAM.

    .. image:: img/camera_run.png
        :width: 500
        :align: center

.. _stt_android:

Come posso utilizzare la modalità STT sul mio dispositivo Android?
------------------------------------------------------------------------

La modalità STT richiede che il dispositivo mobile Android sia connesso a Internet e che sia installato il componente Google.

Segui i passaggi qui sotto.

#. Modifica la modalità AP del file ``galaxy-rvr.ino`` in modalità STA.

    * Apri il file ``galaxy-rvr.ino`` situato nella directory ``galaxy-rvr-main\galaxy-rvr``. 
    * Poi commenta il codice relativo alla modalità AP. Decommenta il codice relativo alla modalità STA e inserisci ``SSID`` e ``PASSWORD`` del tuo Wi-Fi domestico.

        .. code-block:: arduino

            /** Configura modalità Wifi, SSID, password */
            // #define WIFI_MODE WIFI_MODE_AP
            // #define SSID "GalaxyRVR"
            // #define PASSWORD "12345678"

            #define WIFI_MODE WIFI_MODE_STA
            #define SSID "xxxxxxxxxx"
            #define PASSWORD "xxxxxxxxxx"

    * Salva il codice, seleziona la scheda corretta (Arduino Uno) e la porta, poi clicca il pulsante **Upload** per caricarlo sulla scheda R3.

#. Cerca ``google`` su Google Play, trova l'app mostrata qui sotto e installala.

    .. image:: img/google_voice.png
        :width: 500
        :align: center

#. Collega il tuo dispositivo mobile alla stessa rete Wi-Fi che hai configurato nel codice.

    .. image:: img/sta_wifi.png
        :width: 500
        :align: center

#. Apri il controller precedentemente creato in SunFounder Controller e collegalo a ``GalaxyRVR`` tramite il pulsante |app_connect|.

    .. image:: img/app/camera_connect.png
        :width: 400
        :align: center


#. Tocca e tieni premuto il widget **STT(J)** dopo aver cliccato il pulsante |app_run|. Apparirà un messaggio che indica che sta ascoltando. Pronuncia i seguenti comandi per muovere il rover.

    .. image:: img/app/play_speech.png

    * ``stop``: Tutti i movimenti del rover verranno fermati.
    * ``forward``: Il rover avanzerà.
    * ``backward``: Il rover si muoverà all'indietro.
    * ``left``: Il rover girerà a sinistra.
    * ``right``: Il rover girerà a destra.

Informazioni sul firmware dell'ESP32 CAM
---------------------------------------------------

Ecco il link per il firmware dell'ESP32 CAM: |link_ai_camera_firmware|


.. ↓ this firmware only for sunfounder controller


.. Q6: How to Flash New Firmware to an ESP32 CAM?
.. ----------------------------------------------------
.. The camera module comes pre-flashed from the factory. However, if you encounter a data corruption issue, you can re-flash it with new firmware using the Arduino IDE. Here's how:

.. **1. Prepare the Programmer**

.. #. First, get a programmer ready.

..     .. image:: img/esp32_cam_programmer.png
..         :width: 300
..         :align: center

.. #. Insert the ESP32 CAM into the programmer and then plug the programmer into your computer.

..     .. image:: img/esp32_cam_usb.jpg
..         :width: 300
..         :align: center

.. **2. Install the ESP32 Board**

.. To program the ESP32 microcontroller, you must install the ESP32 board package in the Arduino IDE. Follow these steps:

.. #. Go to **File** and select **Preferences** from the drop-down menu.

..     .. image:: img/install_esp321.png
..         :width: 500
..         :align: center

.. #. In the **Preferences** window, find the **Additional Board Manager URLs** field. Click on it to enable the text box.

..     .. image:: img/install_esp322.png
..         :width: 500
..         :align: center

.. #. Add this URL to the **Additional Board Manager URLs** field: https://espressif.github.io/arduino-esp32/package_esp32_index.json. This URL links to the package index file for ESP32 boards. Click **OK** to save the changes.

..     .. image:: img/install_esp323.png
..         :width: 500
..         :align: center

.. #.  In the **Boards Manager** window, search for **ESP32**. Click the **Install** button to begin installation. This downloads and installs the ESP32 board package.

..     .. image:: img/install_esp324.png
..         :align: center

.. **3. Install the Libraries**

.. #. Install the ``WebSockets`` library from the **LIBRARY MANAGER**.

..     .. image:: img/esp32_cam_websockets.png
..         :width: 500
..         :align: center

.. #. Follow the same steps to install the ``ArduinoJson`` library.

..     .. image:: img/esp32_cam_arduinojson.png
..         :width: 500
..         :align: center

.. **3. Download and Upload Firmware**

.. #. Download the firmware file.

..     * :download:`ai-camera-firmware <https://github.com/sunfounder/ai-camera-firmware/archive/refs/heads/main.zip>`

.. #. Extract the downloaded firmware file and rename the extracted folder from ``ai-camera-firmware-main`` to ``ai-camera-firmware``.

..     .. image:: img/esp32_cam_change_name.png
..         :align: center

.. #. Open ``ai-camera-firmware.ino`` with the Arduino IDE, which also opens the associated code files.

..     .. image:: img/esp32_cam_ino.png
..         :align: center

.. #. Select **Board** -> **esp32** -> **ESP32 Dev Module**.

..     .. image:: img/esp32_cam_board.png
..         :width: 500
..         :align: center

.. #. Choose the correct port.

..     .. image:: img/esp32_cam_port.png
..         :width: 400
..         :align: center

.. #. Ensure to enable **PSRAM** and select **Huge APP** in the **Partition Scheme**.

..     .. image:: img/esp32_cam_psram.png
..         :width: 400
..         :align: center

.. #. Finally, upload the firmware to the ESP32 CAM.

..     .. image:: img/esp32_cam_upload.png
..         :width: 500
..         :align: center

.. #. After successful firmware upload, you can find more information at this link: https://github.com/sunfounder/ai-camera-firmware.



