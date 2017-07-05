Instructions to run the build alexa-avs sample application
===========================================================
1.- Download the image alexa-conexant-picopi-imx7.sdcard into the pico-pi board
2.- Boot Linux on the pico-pi board
3.- Connect your board to the internet. Could be by using ethernet or wireless connection
    a) Ethernet: Plug the ethernet cable
    b) Wireless: run the script under /home/root/wifi_start.sh. Follow the instructions shown by the script.
4.- Clone the alexa-picopi-autobuild.git repo
    $git clone http://sw-stash.freescale.net/scm/vs/alexa-picopi-autobuild.git
    $cd alexa-picopi-autobuild
5.- Run the automated_install.sh script. Follow the instructions from the script.
    $bash automated_install.sh
    The script will eventually ask for the ProductID, ClientID or ClientSecret. Make sure you have those values in place.
6.- After the script has been finished, the following commands have to be run in separte terminals from a vnc client connection.
    Run the companion service: cd /home/root/alexa-avs-sample-app/samples/companionService && npm start
    Run the AVS Java Client: cd /home/root/alexa-avs-sample-app/samples/javaclient && mvn exec:exec
    If wake word agent was enabled
    Run the wake word agent:
    Sensory: cd /home/root/alexa-avs-sample-app/samples/wakeWordAgent/src && ./wakeWordAgent -e sensory

