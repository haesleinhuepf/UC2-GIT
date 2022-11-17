# Michelson Interferometer

We built our Michelson interferometer using 3D printed, low-cost UC2 cube blocks and optical components. In the next chapters, you will find basic information about Michelson Interferometer, setup diagram, necessary UC2 modules, printing details, additional components, assembling contents and final results of our UC2- Michelson Interferometer setup.



_Michelson Interferometer_ is an optical interferometer which measures some factors of light beams such as length, surface irregularities, and refraction index. It is used for testing lenses or prisms, measuring refraction index or minute details of surfaces in optical industry.

<p align="center">
<img src=".\IMAGES\UC2_Setups_8_michelson.png"
width="450">
</p>

The basic mechanism is that Beam-splitter module divides an incoming light beam into two beams, one is transmitted to a fixed mirror and the other is reflected to a movable mirror. Then two beams are reflected by these mirrors (M1 and M2) and interfere with each other with adding or subtracting in Beam-splitter cube.This interference generates a pattern which includes interference fringes of light and dark lines.
Moving screws of the Diagonal Kinematic Mirror Holder cube provides flexibility to interfere two reflected beams in the beam-splitter easily.
In the Results section, interference pattern image of the test setup can be seen.  

<p align="center">
<img src=".\IMAGES\Application_Michelson-Interferometer_v3.png" width="600">
</p>

## <img src="./IMAGES/D.png" width="40">Parts
The [Bill of Materials](https://docs.google.com/spreadsheets/d/1U1MndGKRCs0LKE5W8VGreCv9DJbQVQv7O6kgLlB6ZmE/edit?usp=sharing) is always the most up-to-date version!

### Modules for this setup

|  Name | Properties  |  Price | Link  | # |
|---|---|---|---|---|
|  Baseplate puzzle| - | 5€  | [Base-plate](../../CAD/ASSEMBLY_Baseplate/)   | 7|
|  Module: Laser | - | 18,40 €  | [LASER](../../CAD/ASSEMBLY_CUBE_Laser)  | 1|
|  Module: Beam Expander | It expands incoming laser beam  | 12,10 €  | [Beam Expander](../../CAD/ASSEMBLY_CUBE_Beamexpander)  | 1|
|  Module: Beam Splitter | It splits incoming light beam into two beams and reunites reflected two beams. | 29,20 €  | [Beam Splitter](../../CAD/ASSEMBLY_CUBE_Beamsplitter)  | 1|
|  Module: Kinematic Mirror | - | 9,22 €  | [ Kinematic Mirror](../../CAD/ASSEMBLY_CUBE_Mirror_Kinematic)  | 2|
|  Module: Raspberry Camera  | - | 33,70 €  | [RasPi Camera](../../CAD/ASSEMBLY_CUBE_RaspiCam)  | 1|

### <img src="./IMAGES/P.png" width="40"> 3D-printing
To acquire the STL-files use the [UC2-Configurator](https://uc2configurator.netlify.app/). The files themselves are in the [RAW](../../CAD/RAW/STL) folder. The module can be built using injection-moulded (IM) or 3D-printed (3DP) cubes.

## <img src="./IMAGES/B.png" width="40"> Additional components
* Check out the [RESOURCES](../../TUTORIALS/RESOURCES) for more information!
*  32× - 68× 5mm Ball magnets [🢂](https://www.magnetladen.de/kugelmagnet-5-mm-n42-nickel/)
* 32× - 42× Screws DIN912 ISO 4762 M3×12 mm [🢂](https://eshop.wuerth.de/Zylinderschraube-mit-Innensechskant-SHR-ZYL-ISO4762-88-IS25-A2K-M3X12/00843%20%2012.sku/de/DE/EUR/)
* 1× M3×30 mm and M3 nut - non-magnetic
* 3× Mirrors (e.g. 30×30 mm² Toymirrors) [🢂](https://www.amazon.de/Rayher-14548606-Spiegelmosaik-selbstklebend-SB-Btl/dp/B008KJ8438/ref=pd_bxgy_201_img_3/258-8761405-4543762?_encoding=UTF8&pd_rd_i=B008KJ8438&pd_rd_r=80fd534c-997b-4a19-b91a-9bf38dbf4ade&pd_rd_w=4DEXV&pd_rd_wg=7SLRE&pf_rd_p=98c98f04-e797-4e4b-a352-48f7266a41af&pf_rd_r=N95R9S45MNSYNQX2BAJE&psc=1&refRID=N95R9S45MNSYNQX2BAJE)
* 1x Green Laser [🢂](https://www.laserlands.net/11051047.html)
* 1× RasPi Camera [🢂](https://www.amazon.de/Raspberry-Pi-v2-1-1080P-Kamera-Modul/dp/B01ER2SMHY/ref=sr_1_4?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=1LUZK9XHFS5CX&keywords=raspberry+pi+camera+v2.1&qid=1565008837&s=gateway&sprefix=raspberry+pi+camera+%2Caps%2C163&sr=8-4)
* 1× RasPi Camera long cable [🢂](https://www.amazon.de/gp/product/B075JN61S7/ref=ox_sc_act_title_2?smid=A1X7QLRQH87QA3&psc=1)
* 2× M2 screw + nut [🢂](https://www.amazon.de/Edelstahl-Sechskopf-Knopf-Schrauben-Unterlegscheiben-Sortiment-Aufbewahrung/dp/B073SS7D8J/ref=sr_1_fkmr0_1?__mk_de_DE=%C3%85M%C3%85%C5%BD%C3%95%C3%91&keywords=zylinderkopfschrauben+set+galvanisiert&qid=1565007371&s=diy&sr=1-1-fkmr0)
* 1x Iphone Lens [🢂](https://www.ebay.com/c/7029261375)
* 1x Planoconvex Lens f'=26,5mm, 18 mm (551.OAL)[🢂](https://www.pgi-versand.de/?id=47&mode=artdet&artnr=551.OAL)
* 1x Beamsplitter Cube (Art. 2137) [🢂](https://optikbaukasten.de/)


## <img src="./IMAGES/A.png" width="40"> Assembly
For assembly instructions of the respective modules refer to the links in Modules for this setup.


## <img src="./IMAGES/E.png" width="40"> Results
We built Michelson Interferometer using injection molding UC2 cubes. Experiment setup looks:
<p align="center">
<img src="./IMAGES/Michelson 2.JPG" width="300">
</p>

<p align="center">
<img src="./IMAGES/Michelson .JPG" width="300">
</p>

Interference pattern looks like:

<p align="center">
<img src="./IMAGES/interference pattern.png" width="300">
</p>

## Suggestions

We are really happy to see you there. If you have any problems or new ideas, please try it or suggest us! We are an open-source project and ready to hear new voices :hugs:
