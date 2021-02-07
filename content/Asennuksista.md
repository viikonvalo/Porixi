+++
Date = "2021-02-06T17:16:59.200Z"
Title = "Asennuksista"
Description = "Asennuksista"
Luokat = ["Teeitse"]
menu = ["teeitse"]
weight = 100
+++

Ubuntun asennusohjeita - Prologi
================================

{{< menuinclude file="/static/malline/Asennuksista-menu.md" >}}

Tämä ohje on kirjoitettu muistilistaksi omien kokemusten pohjalta
U/K/Xubuntu 7.10 asennuksista vanhoihin i386 32bit koneisiin ja
muutamiin kannettaviin. Esitän tässä ne seikat joihin itse olen
törmännyt ubuntun asennuksissa ja miten ne olen selvittänyt.

Kannettavat
-----------

Nämä ohjeet käsittelevät pääasiassa 3D-ominaisuuksien ja langattoman
verkon käyttöönottoa.

### HP Compaq 9000

[HP Compaq NX9000](/HP_Compaq_NX9000 "wikilink")

HP NX9000 koneessa toimii lähes kaikki suoraan jo Ubuntu 7.10
asennuksessa, mutta näytönohjaimen kanssa saa hieman painiskella.

Ohjeessa kerrotaan kuinka näytönohjaimen ajuri otetaan käyttöön sekä
asennetaan työpöytäsomisteet ja tv-out toimimaan.

### Acer Travelmate 3020

[Acer_Travelmate_3020](/Acer_Travelmate_3020 "wikilink")

Acerin koneet ovat hieman kinkkisiä, mutta näillä ohjeilla sain itse
asennettua langattoman verkon sekä työpöytäsomisteet helposti.

### Lenovo R61i

Tämä oli helppo tapaus. Ubuntu Hardy Heron romppu asemaan, boottaus ja
se on siinä. Ubuntu pienensi esiasennettuna olleen Vistan levyosiota, ja
vapautuneeseen tilaan asentui Linux. Ilman säätelyä toimi äänet,
lepotila ja lepotilasta käynnistyminen, WLAN, 3D-kiihdytys (Intelin
näytönohjain, mallia saatavilla myös NVidian piirillä, mutta tällöin 3D
vaatii NVidian suljetun binääriajurin ja kuulemma lepotila ei toimi).
Kaikki mitä on kokeiltu on toiminut heti. Ostettu
[Mikropasista](http://mikropasi.fi).

### MSI VR 201X

Msi'n mukana tuli Vistan palautus- ja ajurilevykkeet mikä on suht.
harvinaista nykyään. Kiintolevy oli osioitu suht. järkevästi, Vistan
palautusosio 4.13 Gt, C:Vista 34.18 Gt, D:109.01 Gt. Koska
Vista-koneiden tapaan D:-osio oli tyhjä eikä sinne ollut linkitetty
mitään tiedostoja niin poistin sen Ubuntun livelevyn Gparted ohjelmalla
ja asensin Ubuntun käyttäen suurinta vapaata tilaa eli edesmennyttä D:
osiota.

WLANia lukuunottamatta kaikki muut toiminnot pelasivat virittelyittä.
Atheros AR5007EG piiri taas ei alkanut pelittämään jokusen tunnin
säädönkään jälkeen joten 8.04 sai väistyä Ubuntu 8.10 **intrepidin
ibex**in tieltä joka pakettilähteiden säädön ja päivityksen jälkeen
alkoikin pelaamaan WLANin osalta ongelmitta, wpa2 salauksella. Koska
kyseessä on vielä alpha5 versio niin todennäköisesti harrastusta riittää
muilta osin jatkossakin. Ja niinkuin riittikin, päivitykset veivät
atheroksen ajurin sen epävakauden takia?? eikä niitä 8.10 julkaisuun
mennessä tullut takaisin. Ajuri on kuitenkin saatavilla
linux-backports-modules-intrepid paketin avulla.

Päivitystä 1.5-09

Asensin msi'hin 9.04 **Jaunty Jackalopen** alternate levyltä,
alternatella siksi että halusin salatun tiedostojärjestelmän. Kehitystä
on tapahtunut siinä määrin että kone toimi perusasennuksella Wlan
mukaanlukien suoraan ilman mitään säätelyä, edes kryptaus ei tunnu
hidastavan käyttöä merkittävästi.

Ubuntu 9.10 asentui myös ongelmitta, jopa kuulokeliitäntä alkoi
toimimaan niin että kaiuttimet mykistyvät kun kuulokkeet kytkee.

Ostettu [Mikropasista](http://mikropasi.fi). Lisätietoa löytyy
[valmistajan
sivuilta](http://global.msi.com.tw/index.php?func=proddesc&prod_no=1331&maincat_no=135&cat2_no=418).

Oheislaitteiden ajurit
----------------------

### ATI Radeon 9200 (rv280)

[ATI_rv280](/ATI_rv280 "wikilink")

Keräsin tähän joitain huomioita rv280 piirisarjallisen atin n-ohjaimen
asentamisesta. Kyseinen asennus on tehty jollakin ramdom 128mb agp
radeonilla 7.10 xubuntuun.

### Brother DCP-7030 mustavalkoinen monitoimi lasertulostin

Koska tulostimen ppd tiedosto oli hieman hakusessa niin pistänpä ohjeen
tänne. Tulostin asennettiin Ubuntu 8.10 "intrebid ibexiin" ja koska
toimivaa ajuria ei ubuntu toistaiseksi tarjonnut suoraan niin hain ne
[<http://solutions.brother.com/linux/en_us/download_prn.html>](http://solutions.brother.com/linux/en_us/download_prn.html)
sivulta, sekä lpr ajuri että cupswrapper ajuri tarvitaan. Latasin ne
työpöydälle .deb paketteina.

Koska ppd tiedosto haluaisi asentua **/usr/share/cups/model** kansioon
mitä ei kuitenkaan ole luodaan se käskemällä päätteessä "sudo mkdir
/usr/share/cups/model" ja käydään katsomassa ilmestyikö tyhjä model
kansio sinne. Seuraavaksi asennetaan työpöydältä paketit
GDebi-paketinasentajalla tuplaklikkaamalla pakettia sekä klikataan
"asenna paketti". Kun molemmat ajurit on asennettu pitäisi model
kansiossa olla ppd tiedosto.

Cups palvelimen asetukset päästään tekemään selaimella osoitteessa
[<http://localhost:631/>](http://localhost:631/). Tulostimessa saa olla
tässä vaiheessa viimeistään piuhat kiinni ja virrat päällä. Klikataan
Cups hallinta sivulla "Add printer" ja annetaan tarvittavat tiedot,
Siirrytään seuraavaan vaiheeseen "Continue" ja device valikosta valitaan
DCP-7030. Jatketaan, nyt ei välitetä luettelosta mitään vaan "Or Provide
a PPD File:" kohdassa etsitään se ppd tiedosto ja tulostin saattaa jopa
toimia.

**Näillä lääkkeillä tulostin tulostaa ja kopioi, seuraavaksi skannauksen
kimppuun.**

'''Ubuntu 8.04, 8.10 '''

Aluksi avataan "/etc/udev/rules.d/40-basic-permissions.rules" tiedosto
käskemällä päätteessä "sudo gedit
/etc/udev/rules.d/40-basic-permissions.rules" ja muokataan MODE="0664"
tilalle 0666 osiossa

```
# USB devices (usbfs replacement)
SUBSYSTEM=="usb", ENV{DEVTYPE}=="usb_device", MODE="0664"
SUBSYSTEM=="usb_device",                MODE="0664"
eli muotoon
# USB devices (usbfs replacement)
SUBSYSTEM=="usb", ENV{DEVTYPE}=="usb_device", MODE="0666"
SUBSYSTEM=="usb_device",                MODE="0666"
```
Käynnistetään kone uudelleen

**Ubuntu 9.04** Avataan "/lib/udev/rules.d/50-udev-default.rules"
tiedosto ja muokataan "0664" tilalle "0666"

```
# libusb device nodes
SUBSYSTEM=="usb", ENV{DEVTYPE}=="usb_device",   ...   , MODE="0664"
```

Muotoon

```
# libusb device nodes
SUBSYSTEM=="usb", ENV{DEVTYPE}=="usb_device",   ...   , MODE="0666"
```

Käynnistetään kone uudelleen

[Seuraavaksi](Seuraavaksi "wikilink") haetaan ajuri **brscan3** deb
pakettina sivulta
[<http://solutions.brother.com/linux/en_us/download_scn.html>](http://solutions.brother.com/linux/en_us/download_scn.html)
ja annetaan GDebi-pakettien asentajan huolehtia asennuksesta
tuplaklikkaamalla kyseistä deb pakettia ja klikkaamalla asenna jonka
jälkeen skannerin pitäisi toimia*' XSanella*' joka löytyy
sovellukset&gt;grafiikka&gt;Xsane.

**Ubuntu 9.10** Vaihdoin 9.10 versioon päivittämällä edellisestä
versiosta, tulostaminen sujui päivityksen jälkeen suoraan, joten
uskoisin puhtaan asennuksen kanssa 9.04 loitsujen pätevän. Skanneri
sensijaan vaati tiedostoon "/etc/udev/rules.d/z60_libsane.rules"
seuraavan rivin, ennestäänhän tiedosto oli tyhjä.

```
# Brother
SYSFS{idVendor}=="04f9", MODE="0666", GROUP="scanner", ENV{libsane_matched}="yes"
```

### Nokia CS-17 Ubuntu 10.04:ssä, RATKAISTU

Nokian nettitikku/mokkula/3G-modeemi lähti toimimaan Ubuntu 10.04:ssä
kun tein seuraavat toimenpiteet:

1.  SIM-kortilta pitää poistaa PIN-koodin kysely. Jostain kumman syystä
    mokkula pelkästään vilkuttaa punaista valoa jos PIN-koodin kysely on
    päällä. Millään ei päässyt tuosta kohdasta ohi. Nokian Windowsissa
    toimivalla mokkulan mukana tulleella ohjelmistolla voi tämän tehdä,
    tai pistää SIM-kortti kännykkään ja puhelimen valikoista etsiä
    kohdan jolla PIN-koodin kysely otetaan pois käytöstä.
2.  Mokkulan näkyessä muistitikkuna asennetaan sieltä Ubuntu-kansiosta
    Nokia Internet Modem. En oikein tiedä miksi tämä tarvitaan, mutta
    ilman sitä en saanut toimimaan.
3.  Jos on asennettuna Ubuntun pakettivarastosta usb-modeswitch ja
    usb-modeswitch-data, poistetaan ne. Noudetaan uusin usb-modeswitch ,
    [Debianin Experimental-jakelusta](http://packages.debian.org/experimental/usb-modeswitch),
    ja sille pariksi
    [usb-modeswitch-data](http://packages.debian.org/experimental/usb-modeswitch-data).
    Jos experimental-jakelussa ei ole usb-modeswitchiä, on kyseinen
    paketti jo kerinnyt etenemään epävakaaseen jakeluun, eli
    **experimentalin** tilalle pistä **unstable** noihin linkkeihin.
4.  Helpointa on noutaa molemmat paketin sivulta löytyvällä
    imuroi-linkillä, näin saat kaksi .deb-tiedostoa. Ne asennetaan
    komennolla **dpkg --install usb-modeswitch\*.deb** tai jos haluat
    asentaa yksitellen asenna usb-modeswitch-data ensin.

Noiden jälkeen käynnistetään uudelleen, muodostetaan yhteys Network
Managerilla ja pitäisi toimiman.

#### SIM-kortti paikalleen

SIM-kortin saaminen paikalleen oli luvattoman hankalaa. Katso ensin
mukana tulleista ohjeista missä SIM-kortin paikka on ja miten päin se
kuuluu pistää paikalleen. Sitten etsit hyvän valon ja koitat tihruttaa
siihen asennuskoloon. Silloin kun korttia yrittää tunkea paikalleen on
turha katsoa, kortti peittää näkymät tehokkaasti. Siinä asennuskolossa
on oikeassa alanurkassa ohjauskolo, johon kortin se reuna pitää saada
osumaan. Sitten se menee paikalleen kevyesti työntämällä, työnnä niin
pitkälle että kortti on kokonaan mokkulan sisällä ja kansi mahtuu
kiinni.

Mokkulan suunnittelija ei liene huomannut käyttäjien joutuvan asentamaan
SIM-korttia, eikä ainakaan ajatellut miten SIM-kortin saa pois. Keksin
pistää ohuen ruuvimeisselin kärjen kortin alle, sitten painoin sormella
kortin päältä ja vedin korttia ulos. Näin nitkuttamalla sain korttia
ulos sen verran että siihen sai sormilla kiinni ja poistaminen viimein
onnistui.
