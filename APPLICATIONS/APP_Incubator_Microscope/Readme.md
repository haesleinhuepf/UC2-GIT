# In-Incubator Microscope
This is the repository for the in-incubator microscope. It is capable to acquire Time-Lapse videos from living cells inside an incubator.

The current version of the Z-stage is inspired by the flexure-bearing Z-stage from Richard Bowman's openflexure microscope design. Their open-source project can be found [here](https://openflexure.org).

<p align="center">
<img src="./IMAGES/Application_Incubator_Microscope_v3.png" height="500">
</p>

Each functional block has an Arduino acting as a BUS-communicator. Therefore it's possible to control (i.e. switch on/off) devices from the MASTER-device (i.e. Raspberry pi). We aim to build a low-cost solution for high throughput acquisitions, acting as a new tools for (not only) biologists.

It is a very early developer version. Please feel free to contribute to the documentation and device development.

<p align="center">
<img src="./IMAGES/Application_Incubator_Microscope_v3_2.png" height="400">
</p>

Note: The pictures on this site do not show the latest version of the Z-stage. Follow the respective assembly guidelines.

## <img src="./IMAGES/F.png" width="40">Devices features:

* X/Y/Z/t Acquisitions possible
* Fluorescent imaging
* Quantitative Phase Imaging
* Modularized design
* Low-cost acquisition
* Based on off-the-shelf components
* Open-Source

## <img src="./IMAGES/D.png" width="40">Parts
The [Bill of Materials](https://docs.google.com/spreadsheets/d/1U1MndGKRCs0LKE5W8VGreCv9DJbQVQv7O6kgLlB6ZmE/edit?usp=sharing) is always the most up-to-date version!

### Modules for this setup

|  Name | Properties  |  Price | Link  | # |
|---|---|---|---|---|
|  Baseplate puzzle| - | 5€  | [Base-plate](../../CAD/ASSEMBLY_Baseplate/)   | 5|
|  Module: Z-Stage | -  | ?? €  | [Z-Stage](../../CAD/ASSEMBLY_CUBE_Z-STAGE_sample)  | 1|
|  Module: Mirror 45°  | - | 5€  | [Mirror 45](../../CAD/ASSEMBLY_CUBE_Mirror_45)  | 1|
|  Module: Raspberry Camera  | - | ??€  | [RaspiCam](../../CAD/ASSEMBLY_CUBE_RaspiCam)  | 1|
|  Module: LED array  | - | ??€  | [LED array](../../CAD/ASSEMBLY_CUBE_LED_Matrix)  | 1|

### <img src="./IMAGES/P.png" width="40"> 3D-printing
To acquire the STL-files use the [UC2-Configurator](https://uc2configurator.netlify.app/). The files themselves are in the [RAW](../../CAD/RAW/STL) folder. The module can be built using injection-moulded (IM) or 3D-printed (3DP) cubes.


## <img src="./IMAGES/B.png" width="40"> Additional components
* Check out the [RESOURCES](../../TUTORIALS/RESOURCES) for more information!
* 1× LED-Array, Neopixel, 8x8 [🢂](https://www.amazon.de/AZDelivery-Matrix-CJMCU-8-Arduino-Raspberry/dp/B078HYP681/ref=sr_1_2?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=neopixel+matrix&qid=1565008576&s=gateway&sr=8-2)
*  32× 5mm Ball magnets [🢂](https://www.magnetladen.de/kugelmagnet-5-mm-n42-nickel/)
* 20× - 40× Screws DIN912 ISO 4762 M3×12 mm [🢂](https://eshop.wuerth.de/Zylinderschraube-mit-Innensechskant-SHR-ZYL-ISO4762-88-IS25-A2K-M3X12/00843%20%2012.sku/de/DE/EUR/)
* 1× M3×30 mm and M3 nut - non-magnetic
* 2× M2×12 mm and 2× M2 nut - non-magnetic
* 1× Raspberry Pi Camera [🢂](https://www.amazon.de/Raspberry-Pi-v2-1-1080P-Kamera-Modul/dp/B01ER2SMHY/ref=sr_1_4?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=1LUZK9XHFS5CX&keywords=raspberry+pi+camera+v2.1&qid=1565008837&s=gateway&sprefix=raspberry+pi+camera+%2Caps%2C163&sr=8-4)
* 1× Objective Lens (e.g. 10×, NA 0.3) [🢂](https://de.aliexpress.com/item/32947647522.html?spm=a2g0x.search0104.3.54.6cf57a4c3DwsTO&transAbTest=ae803_3&ws_ab_test=searchweb0_0%2Csearchweb201602_6_10065_10130_10068_10890_10547_319_10546_317_10548_10545_10696_10084_453_454_10083_10618_10307_537_536_10902_10059_10884_10887_321_322_10103%2Csearchweb201603_6%2CppcSwitch_0&algo_pvid=06d972be-b176-4446-8665-56d9e61a8d2c&algo_expid=06d972be-b176-4446-8665-56d9e61a8d2c-7)
* 1× Mirrors (e.g. 30×30 mm² Toymirrors) [🢂](https://www.amazon.de/Rayher-14548606-Spiegelmosaik-selbstklebend-SB-Btl/dp/B008KJ8438/ref=pd_bxgy_201_img_3/258-8761405-4543762?_encoding=UTF8&pd_rd_i=B008KJ8438&pd_rd_r=80fd534c-997b-4a19-b91a-9bf38dbf4ade&pd_rd_w=4DEXV&pd_rd_wg=7SLRE&pf_rd_p=98c98f04-e797-4e4b-a352-48f7266a41af&pf_rd_r=N95R9S45MNSYNQX2BAJE&psc=1&refRID=N95R9S45MNSYNQX2BAJE)
* 2× ESP32 [🢂](https://www.amazon.de/AZDelivery-NodeMCU-Development-Nachfolgermodell-ESP8266/dp/B074RGW2VQ/ref=sr_1_3?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=esp32&qid=1565008313&s=gateway&sr=8-3)
* 1× Stepper Motor and 1× Driver Board [🢂](https://www.amazon.de/Elegoo-Stepper-Schrittmotor-28BYJ-48-Treiberplatine/dp/B01MEGIHLF/ref=sr_1_1_sspa?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=stepper+arduino&qid=1565008205&s=gateway&sr=8-1-spons&psc=1)
* 9× Female-Female Jumper Wire, 0.14 mm² [🢂](https://www.amazon.de/ZOORE-120pcs-Multicolored-Female-Breadboard/dp/B07P85V1G3/ref=sr_1_5?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=jumper+male&qid=1565690543&s=industrial&sr=1-5)
* 2× Power cables for ESP32 - USB-microUSB [🢂](https://www.amazon.de/dp/B0778FV6K4/ref=sr_1_2?dchild=1&fst=as%3Aoff&qid=1586361990&refinements=p_89%3AGritin&rnid=669059031&s=computers&sr=1-2)
* Optional (for Fluomodule): 2× Star-LEDs blue (high power 1-3 Watt) [🢂](https://www.ebay.de/itm/Hi-Power-LED-1W-3W-UV-STAR-Ultraviolet-/131326525056?var=)
* Optional (for Fluomodule): 1x MOS-FET/Power PNP Transistor [🢂](https://www.ebay.de/itm/BD809-Transistor-npn-80V-10A-90W-TO220/360661360188?hash=item53f9179e3c:g:ssEAAOSw-fNaqt1l)
* Optional (for Fluomodule): 4× Screws DIN912 ISO 4762 M3×18 mm [🢂](https://eshop.wuerth.de/Zylinderschraube-mit-Innensechskant-SHR-ZYL-ISO4762-88-IS25-A2K-M3X18/00843%20%2018.sku/de/DE/EUR/)

## <img src="./IMAGES/A.png" width="40"> Assembly and alignment
For assembly instructions of the respective modules refer to the links in Modules for this setup.

A simplified scheme can be found [here](./IMAGES/UC2_fullBOX_incubator_EN.pdf).

A detailed alignment instructions are also found [here](../../WORKSHOP/TiM2020).


### Assembling the injection moulded cube-based microscope
<p align="center">
<img src="./IMAGES/image001.jpg" width="500">
</p>

<p align="center">
<img src="./IMAGES/image002.jpg" width="500">
</p>

<p align="center">
<img src="./IMAGES/image003.jpg" width="500">
</p>

<p align="center">
<img src="./IMAGES/image004.jpg" width="500">
</p>

<p align="center">
<img src="./IMAGES/image005.jpg" width="500">
</p>

<p align="center">
<img src="./IMAGES/image006.jpg" width="500">

</p><p align="center">
<img src="./IMAGES/image007.jpg" width="500">
</p>

<p align="center">
<img src="./IMAGES/image008.jpg" width="500">
</p>

<p align="center">
<img src="./IMAGES/image009.jpg" width="500">
</p>




## <img src="./IMAGES/L.png" width="40"> Electronics
🢂 Find more in the [Electronics section](../../ELECTRONICS)

## <img src="./IMAGES/W.png" width="40"> Software
🢂 Find the software for this setup in our dedicated [UC2-Software-GIT](https://github.com/bionanoimaging/UC2-Software-GIT)

## <img src="./IMAGES/E.png" width="40"> Results

This is a 30-minutes timelapse of some dog-cells made in a Workshop in UiO prepared by Xian H. and Kay S.

<p align="center">
<img src="./IMAGES/SAMPLE.gif" width="500">
</p>

## <img src="./IMAGES/S.png" width="40"> Participate!

Do you want to show your own results? Do you have ideas for improvements? Let us know!
