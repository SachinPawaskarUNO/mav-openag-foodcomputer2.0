# **Issues Faced During Development**
:house: [Back to Main](https://github.com/SachinPawaskarUNO/mav-openag-foodcomputer2.0/blob/master/docs/CompleteGuideFoodComputer.md)

# *Remote Connection - Raspberry PI*

First key issue was establishing a stable WiFi environment in the PKI Guest Wireless network.  This initially cause great frustration as it led to unnecessary troubleshooting.

With the help of a HDMI cable and a monitor, we initially connected the HDMI port of the PI to a monitor and configured wireless connection.

All the wireless connections once configured will be available in the "wpa_supplicant.conf" file, the path is located here- /etc/wpa_supplicant/wpa_supplicant.conf

> <img src="./media/image10.png" width="450" height="320" />

So, when you go to a new network and your PI is not configured to the new network, you can still connect by following the steps-

1. Turn On your Hotspot of your android device and change the name of the available Hotspot device to one of the names already available in the wpa_supplicant file.

2. I changed my Hotspot device SSID to UNOGuest and had no password set to it, making it an open network.

3. Connect your laptop to the same network as that of the Raspberry PI.

4. If you have an Angry IP Scanner, run it to know the IP address of the Raspberry PI. If not, download the Scanner- [IP Scanner](http://angryip.org/download/#windows)

5. Use VNC viewer, to connect to the IP of the PI.Download VNC Viewer if you don't have one  here- [Download VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/)
--------------------------------------------

Source : [Our Savior](https://spellfoundry.com/2016/05/29/configuring-gpio-serial-port-raspbian-jessie-including-pi-3/)
