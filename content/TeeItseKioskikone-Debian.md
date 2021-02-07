+++
Date = "2021-02-06T17:17:33.787Z"
Title = "TeeItseKioskikone-Debian"
Description = "TeeItseKioskikone-Debian"
Luokat = []
+++

Debian
======

{{< menuinclude file="/static/malline/TeeItseKioskikone-menu.md" >}}

Laite
-----

Tietokoneena välttää hitaampikin laite. Pitää selvittää mikä on
minimivaatimus mimmoisellekin ohjelmistolle.

Testilaite:

-   AMD Duron 750 MHz 384 Mt
-   levyinä 120 Gt ja 200 Gt IDE-levyt
-   Näytönohjain Matrox Millennium MGA 2064W
-   Asennettiin 60 Gt levyosioon ja yksi 4 Gt swap kummallakin levyllä
-   USB-näppäimistö
-   PS/2 hiiri, kaksipainikkeinen ja kuula

Muutoksia:

-   Käynnistymään vain kiintolevyltä, eli CD, korppu, USB jne. pois
-   BIOS salasana käyttöön, jottei pääse vaihtamaan käynnistyslaitetta
-   Jos ajetaan Live-rompulta, kone käynnistymään vain CD:ltä ja ehkä
    poistetaan kiintolevy ja korppuasema

Ohjelmisto
----------

Asennettiin Debian GNU/Linux 5.02a peruskokoonpano, eli se missä ei ole
X Window mukana eikä muutakaan GUI-sälää. Tämmöisen asennuksen saa
jättämällä lopussa asentamatta Työpöytäympäristön.

Levyosiot ovat turhan isoja, mutta levyillä on muutakin asennettuna ja
tuommoiset osiot sai helposti. Levyä on käytössä juuriosiossa 860 Mt,
eikä muita osiota swappien lisäksi ole käytössä. 2 Gt juuriosio
riittäisi mainiosti, kun vasta 860 Mt on käytössä kaikkien alla
mainittujen ohjelmien asentamisen jälkeen eikä edes **apt-get
autoclean** tai **apt-get clean** ole tehty.

Asennettiin:

-   rcs
-   jed
-   iceweasel-l10n-fi
-   flwm
-   xserver-xorg-video-mga (Koneessa sattui olemaan Matrox Millennium
    -näytönohjaimena)
-   xinit
-   xterm
-   x11-xserver-utils

Kaksi ensimmäistä voi jättää asentamatta jos ei tarvitse versiointia ja
jed teksturina ei miellytä. Paketista x11-xserver-utils tarvitaan xrdb,
jotta sisäänkirjautuessa ei tarvitse kuitata dialogi-ikkunaa xrdb:n
puuttumisesta.

### X Window

Riesaa oli näppäimistön ja hiiren kanssa. X Window käytti
US-näppäinasettelua, piti saada suomalainen näppäinasettelu. Komennolla
X -configure saa pohjaksi tiedoston josta voi muokata
/etc/X11/xorg.conf. Voi vaikka katsoa mallia koneesta jossa suomalainen
näppäinasettelu toimii.

Hiiri temppuili, kun suomalainen näppäinasettelu oli saatu käyttöön
lakkasi hiirikohdistin tyystin liikkumasta eikä hiiren painikkeista
tapahtunut mitään. Ilmeisesti koneen käynnistäminen uudelleen selvitti
sotkun ja hiiri alkoi toimimaan odotetusti. Ennätin kirjoittamaan hiiren
asetuksetkin tiedostoon xorg.conf, voi olla ettei niitä olisi
tarvittukaan vaan rebootti.

Komennolla **X -configure** tehtyä tiedostoa muokataan seuraavasti:
```
--- xorg.conf\~ 2009-08-26 16:08:37.000000000 +0300
+++ xorg.conf  2009-08-26 16:13:10.000000000 +0300
@@ -31,6 +31,8 @@
Section "InputDevice"
     Identifier  "Keyboard0"`  
     Driver      "kbd"`
\+    Option "XkbModel" "pc105"
\+    Option "XkbLayout" "fi" EndSection
Section "InputDevice"
```

Eli lisätään nuo kaksi +-merkittyä riviä. Sitten toimii suomalainen
näppäinasettelu, kun tiedosto on kopioitu nimelle
**/etc/X11/xorg.conf**.

### Selain

Seuraava tiedosto **kioskiselain.sh** tekee iceweaselin (Firefoxin nimi
Debian GNU/Linuxissa) joka käynnistyy uudelleen heti kun sen sulkee.
Rivin sleep 2 voi ottaa pois sitten kun kaikki toimii, se on hyvä olla
jotta on kaksi sekuntia aikaa painaa Control-C jos jostain syystä
täytyisi katkaista suoritus iceweaselin käynnistysten välissä. Pistetään
tämä tiedosto käyttäjän kotihakemistoon alihakemistoon **bin/**.

```
#!/bin/bash
echo "Selain käynnistyy uudestaan heti."
while true ; do
    /usr/bin/iceweasel sleep 2
done
```

Tiedosto **.xinitrc** tarvitaan kun X Window käynnistetään komennolla
**startx**. Se määrää mitä ohjelmia X istuntoon käynnistetään.
Normaalisti tiedoston viimeinen komento on ikkunointiohjelma eli joku
ikkunamanageri. Nyt kun halutaan testailla komentotiedostoa kioskiselain
tehdään tiedostosta tämmöinen:

```
#!/bin/bash
/usr/bin/xterm &
\~/bin/kioskiselain.sh
/usr/bin/flwm
```

Kun yllä oleva toimii, ja selaimen kotisivu ja muut asetukset on tehty
sopiviksi, siirrytään seuraavaan vaiheeseen. Selaimen asetuksia voi
katsoa Ubuntua koskevasta luvusta, siellä on mainittu asetukset joilla
selain tyhjentää istunnon aikana kertyneet tiedot. Samoin voi tutkia
kannattaisiko R-Kiosk asentaa.

### Display manager

Vielä pitäisi koneen käynnistyessä saada edellä väsätty kioskikäyttäjä
kirjautumaan sisään X-istuntoon ja käynnistämään vain selain. Tämä
tehtiin asentamalla Debian GNU/Linux versiosta Squeeze (joka tällä
hetkellä on testattava jakelu) paketti nodm. Sen riippuvuudet sallivat
asentamisen Lennyyn.

Asentamalla nodm ei tarvita **startx**-komentoa. Määritetään tiedostossa
/**etc/default/nodm** NODM_USER halutuksi käyttäjäksi ja vaihdetaan
samassa tiedostossa NODM_ENABLED arvoksi true. Tällöin seuraavassa
bootissa tuo käyttäjä kirjautuu sisään X Window istuntoon. Istunnossa
käynnistyy selain ja vain selain kun käyttäjän tiedostoon
**\~/.xsessionrc** kirjoitetaan

```
#!/bin/bash
\~/bin/kioskiselain.sh
```

Tässä vaiheessa X-istunto on sopiva kioskikäyttöön. Vielä on itse selain
muokattava kioskiselaimeksi. Tässä voi käyttää lisäosaa R-Kiosk kuten
luvussa Ubuntu.

Koska nodm:n riippuvuuksissa mainituista paketeista on riittävän uudet
versiot Lennyssä, voi yksinkertaisesti noutaa nodm_0.6-1_i386.deb
-paketin ja asentaa sen komennolla

```
dpkg --install nodm_0.6-1_i386.deb
```

Tein homman hienommalla debiaanitavalla, eli lisäsin testing-jakelun
tiedostoon **/etc/apt/sources.list** ja tein tiedostot
**/etc/apt/preferences** ja **/etc/apt/apt.conf**:

```
Package: nodm
Pin: release a=testing
Pin-Priority: -10

<APT::Default-Release> "stable";
```

Kun Pin-Priority on alle nollan, noutaa APT asennettavan paketit
vakaasta jakelusta, jos samanniminen paketti siellä on. Nyt on
tarkoitus, että vain nodm noudetaan testattavasta jakelusta. Jos ei tee
sopivaa preferences-tiedostoa, haluaa APT päivittää kaikki paketit
joista on testattavassa uudempi versio. Tällä tavalla voi päivittää
tavanomaiseen tapaan, paketteja noudetaan vain vakaasta jakelusta (koska
Default-Relase on vakaa) paitsi nodm joka päivittyy jos testattavaan
jakeluun tulee uusi version nodm:stä.

Vielä jää pulmaksi nodm:n kautta sisäänkirjautuessa tuleva ilmoitus
"Iceweaselin edellinen istunto sulkeutui yllättäen. ...", joka pitää
kuitata pois. Ilmoitus johtunee siitä, ettei selainta saa suljettua
siististi, se kun käynnistyy heti uudestaan ja lopullisesti sammuu vasta
kun nodm killataan pois.

Arvio
-----

Levytilaa kului 860 Mt plus Swap. Muistia oli käytössä noin 120 Mt.
Tällä koneella selailu oli kohtuullisen vikkelää.

Hiiri kannattaisi olla rullahiiri, sormi hapusi rullaa joka kerta kun
selaimein ikkunaa piti vierittää. On niin tottunut rullahiireen että
rullan puute on kömpelöä.

Muistiksi riittäisi 128 Mt. Kahden gigatavun levy riittäisi, kun swappiä
tehtäisiin kaksi kertaa muistin määrä ja loppu juuriosioksi. Tämmöistä
samanlaista asennusta ei kokeiltu muilla suorittimilla, mutta muissa
kokeiluissa pienin suoritin oli Pentium III 550 MHz, eiköhän tämmöinen
kioskidebiankin toimisi sillä sutjakkaasti.

Kokeiltu myös koneessa jossa Pentium III 550 MHz 128 Mt 6,4 GT,
yhdysrakenteinen näytönohjain. Toimii riittävän rivakasti. Pientä
hämminkiä on kun selain käynnistyy pienenä ikkunana, ja jos
ikkunointiohjelmaa ei ole asennettuna ei kokoa saa kasvatettua. Ei auta
-height ja -width tarkentimet komentorivillä eikä X Window:n -geometry.

--Taleman 21. elokuuta 2009 kello 05.04 (UTC)
