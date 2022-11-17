# An up-to-date tutorial is found in the [UC2 Software GitHub repository](https://github.com/bionanoimaging/UC2-Software-GIT/blob/master/GUI/RASPBERRY_PI/README.md)


      This section and all related sections need an update!

# Getting a UC2-ready Raspbian

This shell script simplifies the preparation of a fresh [Raspbian Stretch Desktop (2018-10-09)](https://www.raspberrypi.org/downloads/raspbian/)
install in order to use (coming soon) UC2 related software . A python touch app allowing software control of an UC2 microscope is already in the pipe
and requires a lot of dependencies such as a proper install of [OpenCV](https://opencv.org) and [kivy](https://kivy.org/#home) among others.
Setting up all dependencies manually is time consuming and error-prone for beginners. This script is supposed to be an (almost) one-click solution
taking care of this in order to get you started right at the imaging part.

## Prerequisites

* RaspberryPi 3B+
* Micro-SD-Card with at least 8GB
* Image of [**Raspbian Stretch Desktop**](https://www.raspberrypi.org/downloads/raspbian/) (at least version of 2018-06-27)
* Ready set internet connection on the image
* Making sure the Pi's time and date is correct (SSL-Handshake)

You may try any other RaspberryPi model running one of the above mentioned Raspbian Stretch releases and which provides a WiFi-Interface.
However, this is the setup the script was tested on and validated to work as expected. Tests on the RaspberryPi Zero W showed that installation
of kivy fails due to memory issues, but then again a correctly set-up image in the first place will run fine with kivy on a Pi Zero W.
That says, setting up the image on a 3B+ with this script and then use the very same SD-card (or image of it) on a Pi Zero W showed to be working as intended.

**The shell script UC2_install.sh assumes running on a fresh Rasbian Stretch Desktop image. We take no responsibility for any damage or loss introduced by this script.**

## Security

Raspbian ships with a commonly well-known default username and password. Although you was prompted to change the password for the default user pi,
immediately after first boot, the commonly known user name keeps being quite a security issue (attack-vector) in combination with active SSH. Remember,
intruders to your RaspberryPi are at this point intruders to your whole local network probably trusting the RaspberryPi.

**For security reasons we therefore highly recommend to create a new user with a new password prior to running this script!**

* Open a terminal window and create a new user with a name of your choice with: (replace without brackets; non-caps)
```
$ sudo adduser <yournewusername> --gecos ""
```
* You will be prompted to choose a new password for the newly created user
* Please reboot when done. Re-login to user pi is no problem and expected by the script
* Installation will switch to the newly created user's profile by itself
* FYI: The install script itself does *never* know your or any logged-in user's password!

## Installing

* Flash one of the above mentioned Stretch releases onto the SD-Card (e.g. with Etcher on Windows)
* Put the just flashed SD-card into the RaspberryPi, connect the RaspberryPi to a display and power it up
* Connect a keyboard and/or mouse to the USB-connectors in order to be able to insert instructions below
* Change password for the default user pi to a secure one on OS prompt
* Set up your internet connection and locale settings right after booting
* Open a terminal and create UC2 folder in home directory
```
$ mkdir -p ~/UC2
```
* Download **UC2_install.sh** from repository and place it into that folder
```
$ wget https://raw.githubusercontent.com/bionanoimaging/UC2-GIT/master/RASPBERRY-PI/UC2_install.sh -P ~/UC2/
```
* Make sure the file has executable rights
```
$ sudo chmod a+x ~/UC2/UC2_install.sh
```
* Make sure time and date of the RaspberryPi are correctly set if out of sync. (replace date, time and timezone appropriately)
```
$ sudo date -s "Tue Oct 30 16:07:41 CET 2018"
```
* Now you are ready to run the script with sudo (see details for further information)
```
$ sudo sh ~/UC2/UC2_install.sh
```
* Installation will take approx. 90min (on model 3B+)
* Once the installation has finished you will be notified by the the Terminal window given in the screenshots below
* ***Please close this notifying window immediately once you become aware the installation completed successfully!***

* Now open a regular terminal and enable future-needed interfaces by typing
```
$ sudo raspi-config
```
* In the interactive menu browse to **Interfacing Options**
	* enable SSH
	* enable I2C
	* enable Camera

### Details
If you created a new user as recommended this new user will be equipped with sudo rights by the script and the installation will switch
to the new user's profile automatically. In case no new user was created it will run on the currently logged-in user's profile.

The script will fetch other installation files by itself and manage necessary reboots on its own continuing installation with sudo rights
afterwards. Although it is generally possible to stop and resume installation at a given point it is recommended to not interrupt the
installation or do anything else on the RaspberryPi in parallel. Once running, the setup script does not need any other user intervention
and will notify you when it is done. Insight on what operations the script performs is given by the script itself. However, in the following
is a short summary of the major packages installed to the system:

* OpenCV 2.4.9.1 (Image-processing Library)
* kivy 1.10.1 (UI-Provider)
* Cython 0.28.2 (C-Compiler for Python)
* numpy (Math library for Python)
* libmtdev (Touchscreen drivers)
* smbus-cffi (I2C-drivers for Python)
* hostapd (Host access point daemon)

Beside that, the RaspberryPi will be turned into an access point, i.e. the RaspberryPi will create an own network with dedicated SSID where the
RaspberryPi is the server. This allows the user to establish a direct SSH connection to the Pi, even when there is no other network
(e.g. no internet connection) taking care of the routing. In addition, if the Pi has an internet connection it allows you to access
this internet connection while actually being connected to the RaspberryPi's network. The credentials of the RaspberryPi's own network default to:

* SSID: UC2_RaspberryPi_APxxxxx
* PWD: UCInsecurity2
* Server-IP: 192.168.50.1
* Server-Broadcast: 192.168.50.*

These credentials may be adjusted in the file **/etc/hostapd/hostapd.conf** (SSID-Password) or in **/etc/systemd/network/12-ap0.network** respectively
and should take effect after a reboot. If you need to add a new SSID after the install script was run, you will have to add it to
**/etc/wpa_supplicant/wpa_supplicant-wlan0.conf**. The ability to access the internet over the RaspberryPi's network may be restricted
by the internet providing networks firewall (e.g. eduroam). On a regular home router with WPA2 it should work though.

If you encounter problems with your prior-to-install working internet connection, please check the files mentioned in the preceding paragraph in
and replace obvious nonsense entries by something appropriate (e.g. [country code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)).
Changes will take effect after a reboot. If your problem persists please open an issue. Your final terminal screen should look like this:

![Network once finished](./images/finish_network.png)

### Backups

System-relevant files touched by this script are backed-up prior to modification under ~/UC2/backups with an identifying prefix (e.g. "boot" or "lxde")
Following files might be recovered after a successful run:

* /etc/sudoers (etc_sudoers.bak)
* /boot/config.txt (boot_config.bak)
* /etc/network/interfaces (etc_net_interfaces.bak)
* /etc/resolvconf.conf (etc_resolvconf.bak)
* ~/.config/lxpanel/LXDE-pi/panels/panel (lxde_panel.bak)
* ~/.config/lxsession/LXDE-pi/autostart (lxde_autostart.bak)
* ~/.kivy/config.txt (kivy_config.bak)

In case it turns out to be highly demanded we will consider providing script reverting system-relevant changes.

### Acknowledgements

Credits go to [Ingo](https://raspberrypi.stackexchange.com/users/79866/ingo) for providing a neat tutorial for [establishing the access point](https://raspberrypi.stackexchange.com/questions/89803/access-point-as-wifi-repeater-optional-with-bridge)
