+++
Date = "2021-02-06T17:17:41.446Z"
Title = "Windowsin ylläpidosta"
Description = "Windowsin ylläpidosta"
Luokat = []
menu = ["teeitse"]
weight = 1200
+++

[Vapaita ohjelmia](http://valocd.fi) voi käyttää vaikkei tietokoneessa
olisikaan vapaata
[käyttöjärjestelmää](http://fi.wikipedia.org/wiki/Käyttöjärjestelmä).
Tästä syystä pistetään tähän sivulle ohjeita miten Windows pidetään
sujuvan käytön mahdollistavassa kuosissa. Tietoturva- ja muut
päivitykset tulisi siis tarkistaa riittävän usein, ainakin viikoittain.

Yleistä tärkeää
---------------

Windows osaa mennä lepotilaan tai keskeytystilaan, josta käynnistyminen
on nopeaa ja jatketaan siitä mihin jäätiin. Tämä on kätevä ominaisuus
varsinkin akkukäytön varassa läppärissä; kannattaa käyttää niin akku
säästyy. Mutta osa päivityksistä tulee käyttöön vasta kun järjestelmä on
sammutettu ja käynnistetty uudestaan. Lepotila tai keskeytystila ei ole
tämmöinen sammutus. Huolehdi siis, että järjestelmä vaikka **kerran
viikossa** sammutetaan **virrat pois** tilaan. Tällöin seuraavalla
käynnistyskerralla otetaan käyttöön asennetut päivitykset, nekin jotka
vaativat uudelleenkäynnistyksen.

Kannattaa tehdä jokaiselle käyttäjälle **oma käyttäjätunnus**, jolla ei
ole pääkäyttäjän oikeuksia. Pitää siis sen pääkäyttäjän erillään ja
käyttää sitä vain silloin kun pääkäyttäjän oikeuksia tarvitaan, ohjelmia
asennettaessa esimerkiksi. Osa haittaohjelmista on käyttäjäkohtaisia,
eli kirjautumalla toisena käyttäjänä pääsee tietokonetta käyttämään
normaalisti (ja poistamaan sitä haittaohjelmaa). Esimerkiksi
[poliisivirus](http://www.poliisi.fi/poliisi/ita-uusimaa/home.nsf/PFBD/7FF2D302EBAEE133C22579BB004C2A53)
tuntuu olevan vain yhdellä käyttäjällä. Haittaohjelman aiheuttamaa
haittaa saa rajoitettua kun tartunnan saaneella käyttäjätunnuksella ei
ole pääkäyttäjän oikeuksia.

Palomuuri
---------

Tarkista palomuurin olevan käynnissä. Jos palomuuri on esimerkiksi
ADSL-reitittimessä, ei ole välttämätöntä pitää sisäverkon koneissa
palomuuria, kunhan sisäverkon kaikkiin koneisiin ja käyttäjiin voi
luottaa. Gibson Research Corporationin [Shields Up!
-sivulla](http://grc.com) voi tarkistaa palomuurin olevan käynnissä.

**Windows XP**  
Ohjauspaneelista löytyy Tietoturvakeskus, siis Käynnistä |
Ohjauspaneeli | Tietoturvakeskus . Katso samalla palomuurin lisäksi
myös automaattisten päivitysten ja virustorjunnan olevan käytössä. Pistä
automaattinen päivitys käynnistymään semmoiseen kellonaikaan, että
tietokone on useimmiten käynnissä.

<!-- -->

**Windows Vista**  
Ohjauspaneelissa "Perinteinen näkymä" näyttää Tietoturvakeskuksen
käynnistyskuvakkeen samanlaisena kuin XP:ssä. Se toinen näkymä on
"Ohjauspaneelin pääikkuna", ja siinä "Suojaus" ja "Tarkista tämän koneen
suojaustila". Toimii kuten XP:ssä.

**Windows 7**  
Ohjauspaneelista "Järjestelmä ja suojaus" ja avautuvassa ikkunassa
Windowsin palomuuri -kohdassa on toiminto "Tarkista palomuurin tila".
Tilan tulisi olla "Käytössä". Toinen tapa on vasemman alanurkan
käynnistyspainikkeesta avautuvaan *Hae ohjelmista ja tiedostoista*
-hakukenttään kirjoittaa **tarkista palomuurin tila**, siitä pääsee
suoraan oikeaan sovellukseen.

**Windows 8**  
En ole kasia käyttänyt, eikä kukaan kasin käyttäjä ole tähän
kirjoittanut ohjetta.  
--[Taleman](/käyttäjä/Taleman "wikilink") 25. syyskuuta
2013 kello 11.51 (EEST)

Päivitykset
-----------

**Tarkista onko**
[**virustorjunta**](http://fi.wikipedia.org/wiki/Virustorjunta) saanut
päivitettyä itsensä mieluiten enintään 24 tuntia sitten. Riippuu
virustorjuntaohjelmasta miten tämä tehdään.

**ESET Antivirus**  
Open Window, näyttää "Version of virus signature database:", suluissa on
päivämäärä muodossa VVVVKKPP. ESET huomauttaa jos Windowsin päivityksiä
on asentamatta, käy asentamassa ne jos nettiyhteys toimii. Alareunan
tehtäväpalkissa olevan ESET-kuvakkeen päällä hiirtä pitämällä näkyy
ponnahdusteksti, josta myös ilmenee virustunnistetietokannan versio ja
päivämäärä.

<!-- -->

**DNA Nettiturva**  
*Näytä päivitykset*

<!-- -->

**Microsoft Security Essentials**  
Kliksauta alareunan tehtäväpalkissa näkyvää ohjelman kuvaketta, paina
"Avaa" popuppia. Etusivulla näkyy "Virus- ja vakoiluohjelmamääritykset",
ajan tasalla tai päivämäärä jolloin ne on viimeksi päivitetty.
Välilehdellä "Päivitä" näkyy päivämäärä ja kellonaika koska määritykset
luotu ja noudettu koneelle. Tunnistetietojen noudon voi pakottaa
tapahtuvaksi nyt välilehden "Päivitä" painikkeella "Päivitä".

<!-- -->

**Avast! Antivirus**  
*Ylläpito*. Näyttää Nykyinen versio ja julkaisupäivä. Toimintapainike
"Päivitä tarkistusosa ja virustunnisteet" tekee päivityksen heti.

<!-- -->

**ClamWin**  
Alareunan ilmoituspalkin oikeassa reunassa on kuvake, siitä saa
toiminnon tarkista päivitykset.

### Windowsin päivitykset

**Windows XP, Vista ja Windows 7**  
Käynnistä | Kaikki ohjelmat | Windows Update -sivusto, valitaan
painike "pika-asennus". Tämä kestää hyvän tovin, pitää vaan odottaa. Kun
päivitykset on asentuneet ja Windows käynnistetty uudestaan jos
päivitysohjelma sitä halusi, tarkista vielä uudestaan onko päivityksiä.
Windows Update on hieman ärsyttävä, kun se ei osaa noutaa kaikkia
päivityksiä kerralla. Usein se noutaa päivitykset tipoittain, ja pitää
useaan kertaan käydä päivitysrumba läpi.

### Java

Viestintävirasto kirjoittaa
[webbisivullaan](https://www.cert.fi/tietoturvanyt/2012/08/ttn201208301150.html):
> Yksityiskohtaisten ohjeiden sijaan toteamme, että Javan pois kytkemistä
> ainakin www-selaimesta kannattaa harkita.

Jos Javaa ei tarvitse mihinkään, sen poistaminen ei pitäisi haitatakaan.
Javascript on aivan eri asia kuin Java. Javascriptin jos ottaa pois,
alkavat webbisivut tökkimään. Jos päätät pitää javan tietokoneellasi,
varmista asennettuna olevan versio jossa ei ole [tunnettuja vakavia
tietoturva-aukkoja](https://www.cert.fi/tietoturvanyt/2012/08/ttn201208301150.html).
Äläkä vieraile epämääräisillä webbisivuilla.

Java Runtime on tärkeää pitää ajan tasalla tietoturvan takia.
Webbisivuilla on paljon Javaa bling blingiä tekemässä,
tietoturva-aukkoja hyödynnetään ahkerasti. Sivulla [Java
Tester](http://www.javatester.org/) voi käydä tarkistamassa mikä versio
Javasta on koneeseen asennettu. Hieman alempana sivulla on infolaatikko
josta ilmenee mikä on uusin saatavilla olevan Javan versio. Nouda ja
asenna jos uusin ei jo ollut asennettuna. Toinen testisivu on [How do I
test whether Java is working on my
computer](http://www.java.com/en/download/help/testvm.xml), pitkä nimi
sivulla ja toimii hitaammin kuin tuo aiempi linkki.

Javan saa asennettua
[imurointisivulta](http://www.java.com/en/download/help/windows_manual_download.xml).
Java saattaa huomauttaakin saatavilla olevasta uudesta versiosta,
silloin ponnahdusikkunasta pitäisi päästä päivitystoimintoon. Huomaa
Javapäivityksen nykyään suosittelevan, että vanhat Javan versiot
poistetaan ennen uuden asentamista. Löytyy webbisivu
[aiheesta](http://www.java.com/en/download/help/windows_manual_download.xml)
ja [poisto-ohje
windowsissa](http://www.java.com/en/download/help/uninstall_java.xml).

Poisto suomeksi Windows XP:ssä: **Käynnistä | Ohjauspaneeli | Lisää tai poista sovellus**. Sieltä etsitään Java, valitaan ja
merkitään poistettavaksi. Voit noutaa uuden Javan asennustiedoston ennen
kuin poistat vanhan, jotta voit heti saman tien asentaa uuden Javan.
Javan poisto halunnee selaimet suljettaviksi ennen kuin Java suostuu
poistumaan.

### Flash

Myös Flash on webbisivuilla suosittu ja myös herkkä saastuttamaan koneen
haittaohjelmilla. Sivulla [Adobe Flash
Player](http://www.adobe.com/software/flash/about/) voi käydä
tarkistamassa koneeseen asennetun Flash Playerin version. Sivulta
ilmenee myös mikä on uusin julkistettu versio. Päivitä jos on tarpeen
sivulta [Get Flash](http://get.adobe.com/flashplayer/).

Jos selaimesi on Google Chrome, ei Flashiä päivitetä erikseen. Flash
tulee Chromen mukana ja päivittyy kun Chromen uuden version asentaa.

### Selain

Selaimen tulisi olla ajan tasalla, eli päivitettynä uusimpaan versioon.
Lisäksi haittaohjelmien tunkua koneelle selaimen kautta voi tukkia
selaimen lisäosilla. Esimerkiksi [AdBlock](https://adblockplus.org)
estää mainosbannereiden näkymisen, kuulemma poliisivirus tarttuu niiden
kautta.

[NoScript](http://noscript.net/) estää kaikenlaisten scriptien
suorittamisen webbisivulta, tosin usealla sivulla osa
toiminnallisuudesta jää pois jos ei NoScriptille kerro sillä sivulla
olevan sallittua scriptien suorittaminen. Näitä lisäosia pitäisi
löytymän selaimen lisäosien asennuksen kautta. Harmillisesti NoScript
näyttää olevan saatavilla vain Firefoxille ja muille mozillaan
perustuville selaimille.

#### Firefox

Selaimeksi on saatavilla vapaa ohjelma Firefox. Siitäkin tulee uusia
versioita taajaan, monta vuodessa. Firefoxissa luvataan olevan
automaattinen päivitys, mutta se tuntuu toimivan vasta kun Firefoxin
valikosta Ohje | Tietoja Firefoxista käy katsomassa mikä versio on
käytössä. Parempi siis päivittää käsin niin tietää mitä tapahtuu. Katso
Firefoxin versio, Ohje | Tietoja Firefoxista. Sitten webbisivulla
[Firefox-selain](http://www.mozilla.com/firefox/) näkyy mikä on nyt
uusin versio. Päivitä jos tarpeen, sivulla on latauspainike. Tarkista
lataavasi haluamasi kielinen Firefox, siis suomeksi, ruotsiksi,
englanniksi tms..

Valikosta Työkalut | Lisäosat löytyy toiminto Hae päivityksiä oikeasta
yläreunasta (rattaan kuva). Sitä painamalla komennetaan Firefox etsimään
päivityksiä. Valitaan vasemmasta reunasta Liitännäiset. Ruutuun tulevan
listan ylimmäinen kohta on "tarkista ovatko asennetut liitännäiset ajan
tasalla". Sitä painamalla avautuu uusi selainikkuna, joka menee
osoitteeseen
[<https://www.mozilla.org/fi/plugincheck>](https://www.mozilla.org/fi/plugincheck).
Näin saa helposti tarkistettua ovatko kaikki asennetut liitännäiset ajan
tasalla.

Päivityksen jälkeen voi tarkistaa muuttuiko Firefoxin näyttämä versio
katsomalla. Jos ei muuttunut, lienee koneessa asennettuna useita
Firefoxeja. Tämä korjataan **Käynnistä | Ohjauspaneeli | Lisää tai poista sovellus**, etsitään Firefoxeja, valitaan ja merkitään
poistettavaksi. Jos vieläkin käynnistyy vanha versio Firefoxista, ovat
yksittäiset käyttäjät ehkä asentaneet omia kopioitaan. Etsi esimerkiksi
näin (Komentoikkunassa, löytyy Käynnistä | Kaikki ohjelmat |
Apuohjelmat | Komentorivi):

```
c:
cd \\
dir /s firefox.exe
```

Tuon pitäisi löytää kaikki C:-levyllä olevat firefox.exe -tiedostot.

#### Google Chrome

Toinen pätevä selain on [Google
Chrome](https://www.google.com/chrome?hl=fi). Google Chrome pitäisi
osata itse päivittää itsensä, tilanteen voi tarkistaa Muokkaa valikon
toiminnolla "Tietoja Google Chromesta". Näkyy asennettu versio, uusin
versio ja on mahdollista käynnistää päivitys. Jos et löydä tuota kohtaa
valikoista, kirjoita osoiteriville
[`chrome://chrome/`](chrome://chrome/).

#### Internet Explorer

Windowsissa tulee mukana selain Internet Explorer eli IE. Sen vanhat
versiot ovat varsin rikkinäisiä. Windows XP:lle on saatavissa versio 8,
se on ollut ihan hyvä mutta viime aikoina juuri tuosta versiosta on
löytynyt
[tietoturvavikoja](http://www.iltasanomat.fi/digi/art-1288563038637.html)
([CERT
tiedote](http://www.cert.fi/haavoittuvuudet/2013/haavoittuvuus-2013-067.html)).
Uudempiin Windowseihin, siis Vista, Windows 7 ja Windows 8, on
saatavilla IE 9 ja taitaa olla jo versio 10:kin.

IE:n pitäisi päivittyä Windowsin päivitystoiminnolla. Jos näin ei ole
tapahtunut, päivitä itse uusin omaan Windowsiin saatavilla oleva IE.

### Adobe Reader

Adobe Reader on PDF-tiedostojen lukija. Siinäkin voi olla
tietoturvavikoja, eli jostain saatu .pdf -tiedosto saa lukijan
suorittamaan tiedoston laatijan haluamia komentoja. Uusin versio
noudetaan osoitteesta [Adobe Reader](http://get.adobe.com/fi/reader).

Adobe Reader X:ssä on valikossa Ohje toiminto "Tarkista päivitysten
saatatavuus". Se kertoo onko uudempi versio saatavilla.

Jos jokin muu ohjelmisto on käytössä PDF-tiedostojen lukijana, siihen
pätee tämä sama eli kannattaa päivittää uusimpaan julkaistuun versioon.
Esimerkiksi VALO-CD-projektilta saa
[Evincen](http://www.valo-cd.fi/ilmainen_evince).

Hyödyllisiä sovelluksia
-----------------------

Seuraavat ohjelmat eivät kaikki ole vapaita, mutta Windowsin käyttäjille
ne ovat hyödyllisiä. Jos löytyy vastaava vapaa ohjelma, vaihdan sen
tilalle.

-   Sähköpostiin:
    [Thunderbird](http://www.valo-cd.fi/ilmainen_thunderbird), vapaa
    sähköpostiohjelma. Saatavilla myös Linuxiin (Debianissa nimenä on
    Icedove).
-   Windowsin rekisterin korjailuun:
    [CCleaner](http://www.piriform.com/ccleaner). Korjaa rekisterin
    virheitä. Muitakin toimintoja.
-   Kuvankäsittelyyn ja grafiikkaan:
    [GIMP](http://www.valo-cd.fi/ilmainen_gimp): Gnu Image Manipulation
    Program. Piirtää bittikarttakuvia ja osaa [muokata
    valokuviakin](GIMP_pikaohje "wikilink"). Vapaa ja saatavilla
    muillekin käyttöjärjestelmille.
-   Pakkausohjelma: [Valo-CD:n
    7zip](http://www.valo-cd.fi/ilmainen_7zip) tai
    [7-Zip](http://www.7-zip.org/) on ZIP -pakettien purkamiseen ja
    tekemiseen. Osaa muitakin pakkausmuotoja.
-   Videokatselin: [VLC](http://www.valo-cd.fi/ilmainen_vlc) on VideoLAN
    Client. Vapaa ohjelma, osaa soittaa videotiedostoja ja DVD-levyjä.
    Saatavilla Linuxillekin.
-   Tutki prosesseja: [Process
    Explorer](http://technet.microsoft.com/fi-fi/sysinternals/bb896653.aspx)
    on työkalu Windowsin prosessien tutkimiseen. Enemmän ominaisuuksia
    kuin vakiona tulevassa tehtävänhallinnassa. Pelkästään Windowsille
    eikä ole vapaa. Näyttää esimerkiksi millä prosessilla on auki tietty
    hakemisto tai tiedosto.
-   Toimisto-ohjelmat:
    [LibreOffice](http://www.valo-cd.fi/ilmainen_libreoffice). Vapaa ja
    saatavilla muillekin käyttöjärjestelmille. Ohjelmiston nimi oli
    aiemmin OpenOffice.org, nimi muutettiin ja projekti haarautui kun
    Oracle sai sen haltuunsa yrityskaupan kautta.

Katso muutkin Valo-CD:n [ohjelmat](http://www.valo-cd.fi/ohjelmat). Myös
ohjeita löytyy samasta paikasta.
