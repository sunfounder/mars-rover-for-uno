.. note::

    Hello, welcome to the SunFounder Raspberry Pi & Arduino & ESP32 Enthusiasts Community on Facebook! Dive deeper into Raspberry Pi, Arduino, and ESP32 with fellow enthusiasts.

    **Why Join?**

    - **Expert Support**: Solve post-sale issues and technical challenges with help from our community and team.
    - **Learn & Share**: Exchange tips and tutorials to enhance your skills.
    - **Exclusive Previews**: Get early access to new product announcements and sneak peeks.
    - **Special Discounts**: Enjoy exclusive discounts on our newest products.
    - **Festive Promotions and Giveaways**: Take part in giveaways and holiday promotions.

    👉 Ready to explore and create with us? Click [|link_sf_facebook|] and join today!

FAQ
==============

How to Change Wi-Fi Channel?
----------------------------------

The 2.4GHz Wi-Fi band has channels ranging from 1 to 13. ESP32 supports channels 1 to 11. Other devices operating on the same channel may cause interference, leading to connection issues. To mitigate this, you can try changing the channel. By default, the channel is set to 1. When selecting a new channel, it’s recommended to skip 1-2 channels at a time. For example, if the current channel is 1, try channel 3 first, and if the signal is still poor, proceed to channel 5.

.. note::

   ESP32 CAM firmware version 1.4.1 or above is required to change channels. Refer to :ref:`update_firmware` for more details.

#. Power on the GalaxyRVR. To activate the ESP32 CAM, move the mode switch to the **Run** position, and press the **reset** button to reboot the R3 board.

     .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/play_reset.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

#. Find ``GalaxyRVR`` on the list of available networks on your mobile device (tablet or smartphone), enter the password ``12345678``, and connect to it.

     .. note::

        * The current connection is to the GalaxyRVR hotspot, so there is no internet access. If prompted to switch networks, please choose "Stay connected".
        * :ref:`ap_to_sta`

     .. image:: img/app/camera_lan.png
        :width: 500

#. Open a web browser on your mobile device and navigate to ``http://192.168.4.1`` to access the ESP32 CAM OTA update page.

   .. image:: img/faq_cam_ota_141.jpg
      :width: 400

#. Under the **Wi-Fi AP Channel** section, select a different channel. 

   * The default channel is 1. When selecting a new channel, skip 1-2 channels at a time (e.g., from channel 1 to 3, and if needed, to 5).  
   * Click the **Confirm** button to save the changes.

   .. image:: img/faq_cam_ota_channel.png
      :width: 400

#. A confirmation popup will appear, prompting you to reset the device. Click **Confirm**.

   .. image:: img/faq_cam_ota_reset.jpg
      :width: 400
   
#. Press the **Reset** button to reboot the device. The GalaxyRVR is now ready for normal operation.

   .. image:: img/camera_reset.png

.. _update_firmware:

How to Update Firmware for ESP32 CAM
-----------------------------------------

Follow these detailed steps to update the firmware for your ESP32 CAM:

#. Power on the GalaxyRVR. To activate the ESP32 CAM, move the mode switch to the **Run** position, and press the **reset** button to reboot the R3 board.

     .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/play_reset.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

#. Find ``GalaxyRVR`` on the list of available networks on your mobile device (tablet or smartphone), enter the password ``12345678``, and connect to it.

     .. note::

        * The current connection is to the GalaxyRVR hotspot, so there is no internet access. If prompted to switch networks, please choose "Stay connected".
        * :ref:`ap_to_sta`

     .. image:: img/app/camera_lan.png
        :width: 500

#. Click the link below to download the firmware file ``ai-camera-firmware-v1.4.1-ota.bin`` and save it to your mobile device.

   * :download:`ESP32 CAM Firmware <https://github.com/sunfounder/ai-camera-firmware/releases/download/1.4.1/ai-camera-firmware-v1.4.1-ota.bin>`

#. Open a web browser on your mobile device and navigate to ``http://192.168.4.1`` to access the ESP32 CAM OTA update page.

   .. image:: img/faq_cam_ota.jpg
      :width: 400

#. On the OTA page, click the button to select the firmware file.

   .. image:: img/faq_cam_ota_choose.png
      :width: 400

#. Choose the previously downloaded ``ai-camera-firmware-v1.4.1-ota.bin`` file from your device and click **OK**.

   .. image:: img/faq_cam_ota_file.png
      :width: 400

#. Click the **Update** button to start the firmware update process.

   .. image:: img/faq_cam_ota_update.png
      :width: 400
   
#. Wait for the update to complete. Once the displayed version number changes to ``1.4.1``, the update is successful.

   .. image:: img/faq_cam_ota_finish.png
      :width: 400
   
#. After the update is complete, you can close the web browser. Press the **Reset** button to reboot the device. The ESP32 CAM is now ready for normal operation.

   .. image:: img/camera_reset.png

.. _upload_galaxy_code:

How to Upload the ``galaxy-rvr.ino`` Code?
-----------------------------------------------

By default, the GalaxyRVR's Uno R3 board comes preloaded with the necessary firmware, allowing you to control it via APP. If your R3 board has been overwritten with other code, but you'd like to return to the default firmware and continue with the :ref:`quick_start` process, follow these steps to re-upload the code to your R3 board:

#. Use a USB cable to connect the Arduino to your computer. Then, switch the **upload** switch on the rover to the "upload" position.

   .. image:: img/camera_upload.png
        :width: 400
        :align: center

#. Download the required firmware from the link below: 
        
   * :download:`R3 Board Firmware <https://github.com/sunfounder/galaxy-rvr/releases/download/1.1.0/galaxy-rvr-1.1.0.zip>`

#. Extract the downloaded zip file, then double-click the ``update-arduino-firmware.bat`` file to run it.

   .. image:: img/faq_firmware_file.png


#. Type the corresponding number for your GalaxyRVR's Arduino Uno (e.g., ``2``) and press **Enter** to begin the update.


   .. note::

     * If the correct COM port does not appear, or if you're unsure which one it is, disconnect other USB devices from your computer, leaving only the rover connected.  
     * If you encounter an error like "avrdude.exe: stk500_getsync() attempt 1 of 10: not in sync: resp=0xXX", ensure the **upload** switch on the rover is set to the "upload" position, as described in step 1.

   .. image:: img/faq_firmware_port.png

#. After a short while, the new code will be successfully uploaded to the Uno R3 board on GalaxyRVR.

   .. image:: img/faq_firmware_finish.png

.. _ap_to_sta:

Rover Network Configuration: Home WiFi and AP Mode
-----------------------------------------------------

By default, the Uno R3 is preloaded with code configured in AP mode. This means the GalaxyRVR will broadcast a hotspot, allowing you to connect your mobile device to control it via the SunFounder Controller APP.

If you prefer to control the rover using your home WiFi, or need to reset to AP mode for different use cases, follow these steps to upload the modified code to the Uno board:

#. Download the required files from the following link: 

   * :download:`GalaxyRVR Codes <https://github.com/sunfounder/galaxy-rvr/archive/refs/heads/main.zip>`

#. Refer to the installation guide: :ref:`install_arduino_ide`.

#. Use the **Library Manager** to install the ``SoftPWM`` and ``SunFounder AI Camera`` libraries. For detailed steps, see :ref:`install_lib`.

#. Navigate to the ``galaxy-rvr-main\galaxy-rvr`` directory and open the ``galaxy-rvr.ino`` file.

   .. image:: img/faq_galaxy_code.png

#. Comment out lines 69-71, uncomment lines 73-75, replace ``SSID`` and ``PASSWORD`` with your home WiFi credentials.

   .. code-block:: c

      // /** Configure Wifi mode, SSID, password*/
      // #define WIFI_MODE WIFI_MODE_AP
      // #define SSID "GalaxyRVR"
      // #define PASSWORD "12345678"

      #define WIFI_MODE WIFI_MODE_STA
      #define SSID "xxxxxxxxxx"
      #define PASSWORD "xxxxxxxxxx"

#. Connect the GalaxyRVR and computer with a USB cable, and then turn the **upload** switch of the rover to the upload end.

   .. image:: img/camera_upload.png
        :width: 400
        :align: center

#. Click the **Upload** button in the Arduino IDE to upload the modified code to the Uno board.

   .. image:: img/faq_galaxy_upload.png

#. To activate the ESP32 CAM, move the mode switch to the **Run** position, and press the **reset** button to reboot the R3 board. You will then observe a cyan light flashing on the bottom strip.

   .. raw:: html
   
       <video width="600" loop autoplay muted>
           <source src="_static/video/play_reset.mp4" type="video/mp4">
           Your browser does not support the video tag.
       </video>

#. Ensure your mobile device (tablet or smartphone) is connected to your home WiFi network.

   .. image:: img/faq_connect_wifi.jpg
        :width: 400
        :align: center

#. Open the SunFounder Controller App, tap the "+" icon to create a new controller, select the "GalaxyRVR" preset, enter a name or tap "Confirm" to proceed.

   .. image:: img/app/play_preset.jpg
        :width: 600

#. The app will automatically search for the GalaxyRVR. After a moment, you will see a prompt stating "Connected Successfully."

   .. image:: img/app/auto_connect.jpg
        :width: 600
    
#. Now, tap the |app_run| button enables you to view the live video feed from the camera and control the rover using the provided widgets. 

   .. image:: img/app/play_run_view.jpg
        :width: 600 


**Resetting AP Mode**

#. To reset to AP mode and change the SSID and PASSWORD, make sure the AP mode lines are enabled and update the SSID and PASSWORD to the new values. 

   .. code-block:: c

      #define WIFI_MODE WIFI_MODE_AP 
      #define SSID "newSSIDName" 
      #define PASSWORD "newPassword"

      // #define WIFI_MODE WIFI_MODE_STA
      // #define SSID "xxxxxxxxxx"
      // #define PASSWORD "xxxxxxxxxx"

#. Follow the same steps for uploading the code as detailed above.

#. Once uploaded, the GalaxyRVR will broadcast its network with the new network name and password, allowing direct connections without a home WiFi network.


How to Invert the Camera?  
---------------------------

If you find the camera feed upside down while using the SunFounder Controller, you can easily correct it through the app. Follow these steps:  

1. Tap the |app_edit| button in the top-right corner.  

   .. image:: img/app/faq_edit.png  
        :width: 500 

2. Click the **camera** button to open a popup. Toggle the **Inverted** switch to turn it on.  

   .. image:: img/app/faq_inverted.png  
        :width: 500  

3. Save your settings.  

   .. image:: img/app/faq_save.png  
        :width: 500 

4. Return to the control interface and click the |app_run| button.  

   .. note::  

        Occasionally, the camera feed may not appear. If this happens, pause the controller and then click the run button again.  

   .. image:: img/app/faq_run.png  
        :width: 500 
    

.. _install_lib:

Compilation error: ``SoftPWM.h`` or ``SunFounder_AI_Camera.h``: No such file or directory？
---------------------------------------------------------------------------------------------
If you get a “Compilation error: ``SoftPWM.h``: No such file or directory” prompt, it means you don’t have the SoftPWM library installed.

Please install the two required libraries ``SoftPWM`` and ``SunFounder AI Camera`` as shown.

    .. raw:: html

        <video width="600" loop autoplay muted>
            <source src="_static/video/install_softpwm.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>

For the ``SunFounder AI Camera`` library, you need to select "INSTALL ALL" to simultaneously install the required ``ArduinoJson`` dependency.

    .. image:: img/faq_install_ai_camera.png

avrdude: stk500_getsync() attempt 10 of 10: not in sync: resp=0x6e?
-----------------------------------------------------------------------------
If the following message keeps appearing after clicking the **Upload** button when the board and port have been selected correctly.

.. code-block::
    
    avrdude: stk500_recv(): programmer is not responding
    avrdude: stk500_getsync() attempt 1 of 10: not in sync: resp=0x00
    avrdude: stk500_recv(): programmer is not responding
    avrdude: stk500_getsync() attempt 2 of 10: not in sync: resp=0x00
    avrdude: stk500_recv(): programmer is not responding
    avrdude: stk500_getsync() attempt 3 of 10: not in sync: resp=0x00
    At this point, you need to make sure that the ESP32 CAM is unplugged.

The ESP32-CAM and the Arduino board share the same RX (receive) and TX (transmit) pins. So, before you’re uploading code, you’ll need to first disconnect the ESP32-CAM to avoid any conflicts or potential issues.

    .. image:: img/camera_upload.png
        :width: 500
        :align: center

After the code is successfully uploaded, if you need to use the ESP32 CAM, then you need to move the switch to the left to start the ESP32 CAM.

    .. image:: img/camera_run.png
        :width: 500
        :align: center

.. _stt_android:

How can I use the STT mode on my Android device?
------------------------------------------------------------------------

The STT mode requires the Android mobile device to be connected to the Internet and to install the Google service component.

Now follow the steps below.

#. Modify the AP mode of ``galaxy-rvr.ino`` file to STA mode.

   * Open the the ``galaxy-rvr.ino`` file located in the ``galaxy-rvr-main\galaxy-rvr`` directory. 
   * Then comment out the AP mode related code. Uncomment the STA mode related code and fill in  the ``SSID`` and ``PASSWORD`` of your home Wi-Fi.

     .. code-block:: arduino

            /** Configure Wifi mode, SSID, password*/
            // #define WIFI_MODE WIFI_MODE_AP
            // #define SSID "GalaxyRVR"
            // #define PASSWORD "12345678"

            #define WIFI_MODE WIFI_MODE_STA
            #define SSID "xxxxxxxxxx"
            #define PASSWORD "xxxxxxxxxx"

   * Save this code, select the correct board (Arduino Uno) and port, then click the **Upload** button to upload it to the R3 board.

#. Search ``google`` in Google Play, find the app shown below and install it.

    .. image:: img/google_voice.png
        :width: 500
        :align: center

#. Connect your mobile device to the same Wi-Fi as you wrote in the code.

    .. image:: img/sta_wifi.png
        :width: 500
        :align: center

#. Open the controller previously created in SunFounder Controller and connect it to ``GalaxyRVR`` through the |app_connect| button.

    .. image:: img/app/camera_connect.png
        :width: 400
        :align: center


#. Tap and hold the **STT(J)** widget after clicking the |app_run| button. A prompt will appear indicating that it is listening. Say the following command to move the rover.

    .. image:: img/app/play_speech.png

    * ``stop``: All movements of the rover can be stopped.
    * ``forward``: Let the rover move forward.
    * ``backward``: Let the rover move backward.
    * ``left``: Let the rover turn left.
    * ``right``: Let the rover turn right.

Q5: About the ESP32 CAM Firmware
---------------------------------------------------

Here is the firmeware link of ESP32 CAM: |link_ai_camera_firmware|


.. How to Flash New Firmware to an ESP32 CAM?
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

