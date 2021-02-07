+++
Date = "2021-02-06T17:17:39.678Z"
Title = "Ubuntu tutuksi"
Description = "Ubuntu tutuksi"
Luokat = []
menu = ["opiskelu"]
weight = 800
+++

Ohjeita Ubuntun käyttäjille
---------------------------

[Ubuntu](http://www.ubuntu-fi.org/) on yksi
[jakelupaketti](http://linux.fi/index.php/Luokka:Jakelut), eli valmis
kokoelma sovelluksia ja toimiva Linux-järjestelmä.

[Asennusohje](http://wiki.ubuntu-fi.org/Asentaminen) kertoo uusimman
julkaistun Ubuntun version asentamisesta. Jos ei tuon pitkän
asennusohjeen lukeminen innosta, lyhyt ohje jolla perustapauksissa
pärjää on [Asennusohje Ubuntu Suomen
sivuilla](http://wiki.ubuntu-fi.org/Asentaminen).
[Käyttöohjeita](http://wiki.ubuntu-fi.org/Ohjeet) kannattaa lukea
asennuksen jälkeen jos ei omaa aikaisempaa kokemusta Linuxin käytöstä.
[Ubuntu Suomi](http://www.ubuntu-fi.org/) kertoo lisää Ubuntusta
suomeksi.

Aloittelijan parhaaksi tietolähteeksi kehutaan [Ubuntu
tutuksi](http://fi.wikibooks.org/wiki/Ubuntu_tutuksi) -kirjaa, jonka voi
tulostaa paperille ja lukea rauhassa nojatuolissaan. Kirja on ilmainen.

Vinkkejä sekä tiedonjyväsiä
---------------------------

### Suomeksi

Ubuntu 8.04 — 10.04 noutaa kielipaketit asennuksen aikana netistä.
Mikäli nettiyhteys ei asennuksen aikana toimi, jäävät kielipaketit pois
ja Ubuntu ja sovellukset ovat vain suppeasti suomennettuja. Tilanne
korjataan kun nettiyhteys on saatu toimimaan asentamalla paketit
**language-support-fi** ja **language-pack-fi**, esimerkiksi komennolla
sudo apt-get install language-support-fi language-pack-fi

Jos GNOME ei ole kokonaan suomenkielinen, pitää asentaa paketti
**language-pack-gnome-fi**. Vastaavasti KDE:lle **kde-l10n-fi**.

Ubuntun versiosta 9.10 alkaen on saatavilla [Finnish
Remix](http://wiki.ubuntu-fi.org/Ubuntu_Finnish_Remix), jossa on
suomenkielen tuki valmiina CD:llä. Tällöin suomenkieli on kattavasti
tuettu vaikka nettiyhteyttä ei asennuksen aikana olisikaan. Erityisesti
Finnish Remix on hyvä, jos asentaa koneeseen jossa ei ole kunnollista
nettiyhteyttä ja haluaa suomenkielisen Ubuntun, tai haluaa käyttää
suomenkielistä Ubuntua Live-CD:ltä. Jatkossa kuulemma Finnish Remix on
saatavilla julkaistaviin Ubuntun uusiin versioihin.

### Linux työpöydällä

Tavanomaisessa kotikäytössä olevaan työpöytälinuxiin tulisi Ubuntu
10.04:ssä mielestäni asentaa

-   suomenkielen ja muidenkin tarvittavien kielten tuki (Järjestelmä |
    Ylläpito | Kieliasetukset)
-   ubuntu-restricted-extras
-   Medibuntun varastoalue, jotta multimediat alkaa toimimaan
    [Medibuntun oma ohje](https://help.ubuntu.com/community/Medibuntu)
-   xul-ext-adblock-plus eli Adblock+ uudelta nimeltään.

Jos näytönohjain osaa 3D-kiihdytyksen mutta ei ilman epävapaata ajuria,
asennetaan se ajuri: Järjestelmä | Ylläpito | Laiteajurit.

Sitten säädetään näytön tarkkuus sopivaksi, ja kuvaputkinäytön
tapauksessa vielä virkistystaajuuskin (Järjestelmä | Asetukset |
Näytön asetukset).

Jatkossa tarkempia ohjeita miten yllä mainitut jutskat saa asennettua.

#### Multimediaa

Jos tarvitaan Flash-playeriä, javaa tai muuta webbisivuilla yleistä
bling-blingiä kannattaa asentaa paketti **ubuntu-restricted-extras**,
niin saa vähällä vaivalla melkein kaikki lisäkilkeet kerralla.
Asennuksen jälkeen voi mennä sivulle jossa testataan toimiiko Java
selaimessa, esimerkiksi [javatester.org](http://www.javatester.org/)
Sampo-pankin asiakkaan kannattaa valita Sun-Java, muut voivat käyttää
vapaata valintaa.

#### Videot näkymään

Huomasin juuri Ubuntu 15.10 alkaen DVD-levyjen näkymään saattaminen
tehdään eri tavalla. En ole vielä asentanut noin uusia Ubuntuja, mutta
ohjesivu sanoo asennetaan paketti libdvd-pkg. Se ohjesivu on
<https://help.ubuntu.com/community/RestrictedFormats/PlayingDVDs> .

Se vanha systeemi (joka myös selitetään tuossa ohjesivulla) on tuossa
alla.

Ubuntussa ei näy suojatut DVD-elokuvat koska libdvcss ei ole mukana
perusubuntussa. Voi *joko* lisätä Medibuntun varastoalueen, jossa on
muitakin mediapaketteja, *tai* käyttää **libdvdread3**:n mukana tulevaa
asennusscriptiä (scripti noutaa CSS-ohjelman netistä, siis muualta kuin
Ubuntun palvelimilta). Tällöin ei tarvitse lisätä varastoalueita. Ohje
on [Playing
DVDs](https://help.ubuntu.com/community/RestrictedFormats/PlayingDVDs).

##### Asennusscripti

8.04 ja 8.10 Ubuntuissa tehdään: sudo apt-get install libdvdread3
gstreamer0.10-plugins-ugly sudo
/usr/share/doc/libdvdread3/install-css.sh Ubuntu Jauntyssä eli 9.04:ssä
ja uudemmissa Ubuntuissa on **libdvdread4** tuon kolmosen tilalla.

##### Medibuntu

Seuraamalla [Medibuntun omia
ohjeita](https://help.ubuntu.com/community/Medibuntu) saadaan
tarvittavat paketit asennettua jotta videot näkyvät ja kuuluvat. Ubuntu
8.04:ssä pitää suorittaa komennot

```
sudo wget <http://www.medibuntu.org/sources.list.d/hardy.list> -O /etc/apt/sources.list.d/medibuntu.list
sudo apt-get update && sudo apt-get install medibuntu-keyring && sudo apt-get update
sudo apt-get install libdvdcss2 non-free-codecs
```

Katso ettei Synaptic, aptitude tai muu paketinhallintaohjelmisto ole
käynnissä kun yllä olevia komentoja suoritat.

YLE:n uutiset vaativat paketteja **gstreamer0.10-plugins-bad**,
**gstreamer0.10-ffmpeg** ja **gstreamer0.10-plugins-ugly** eli

```
sudo apt-get install gstreamer0.10-plugins-bad gstreamer0.10-ffmpeg gstreamer0.10-plugins-ugly
```
Lähde: [1](https://lists.ubuntu.com/archives/ubuntu-fi/2008-April/000436.html)


YLE:n uutisten, Areenan ja Elävän Arkiston katsomiseen on ohje
[Linux.fi:n](http://linux.fi/index.php/YLE_Areena_ja_Elävä_arkisto)
sivuilla.

### Sampopankki

Sampopankki otti keväällä 2008 uuden käyttöliittymän verkkopankkiinsa.
Se vaati javan selaimeen, vieläpä tietyn version. Tämä on estänyt
Sampopankin verkopankin käyttöä Linuxista, koska Linux-jakeluissa
enimmäkseen ei ollut juuri sitä versiota jonka Sampopankki haluaa.
Sampopankin [minipankki](http://mobiili.sampopankki.fi) toimii kaikissa
selaimissa ja käyttöjärjestelmissä, mutta siinä on pelkistetympi
käyttöliittymä.

Sampopankki lienee nyttemmin korjannut verkkopankkiaan, se toimii
uusimmalla Java runtimella kunhan se on Sun Microsystemsin tekemä java.
Tämä java on saatavilla Ubuntun 10.04 versiossa Partner jakelusta,
vakiojakelussa oleva java runtime ei toimi Sampopankin kanssa. Pitää
siis lisätä Partner -jakelu ohjelmalähteisiin ja asentaa
**sun-java6-plugin**.

Poista työpöytätehosteet käytöstä. Se tapahtuu ainakin Ubuntu Hardyn
Gnome-ympäristössä graafisesti näin: Järjestelmä &gt; Asetukset &gt;
Ulkoasu &gt; Visuaaliset tehosteet &gt; Ei mitään (och samma på svenska
& esim. KDE:ssa puolestaan englanniksi näin: System Settings &gt; Look
and Feel &gt; Desktop &gt; Desktop Effects, uncheck).

Tämän jälkeen pitää sammuttaa selain ja käynnistää selain uudelleen,
jotta se ottaa käyttöön uudet javat. Nyt pitäisi Sampopankin toimia.

Jos verkkopankin java ei lataudu, kokeile [Javan
verifiointia](http://www.java.com/en/download/installed.jsp) tai
[testiapplettia](http://www.java.com/en/download/help/testvm.xml). Jos
nekään eivät toimi ja vaikka selain raportoi Java-pluginin olevan
käytössä, ongelma saattaa liittyä
[ipv6-sidontaan](http://bugs.debian.org/cgi-bin/bugreport.cgi?bug=547457#15).
Silloin täytyy muuttaa tiedostoon */etc/sysctl.d/bindv6only.conf*
sidonta arvoon 0: net.ipv6.bindv6only = 0 Ja käynnistää sysctl
uudestaan: sudo invoke-rc.d procps restart

Viite: [Sampon uusi java verkkopankkiin Ubuntu-fi
Forumilla](http://forum.ubuntu-fi.org/index.php?topic=15190.220)  
Viite: [Linux.fi artikkeli Sammon
verkkopankki](http://linux.fi/wiki/Sammon_verkkopankki)  
Viite: [Ubuntun Java-ohje (englanniksi), näillä ohjeilla ei tarvitse
poistaa vakiojavan asennusta](https://help.ubuntu.com/community/Java)

### Mokkulat

Nettiyhteys matkapuhelinverkossa, siis nämä mobiililajakaista, 3G,
mokkula, nettitikku ja sen semmoiset toimivat Ubuntun versiossa 8.10
oikein hyvin. Tässä ohje: [Matkapuhelin
modeemina](http://wiki.ubuntu-fi.org/Matkapuhelin_modeemina).

Ubuntu 9.10 ei tunnu CD:ltä asennettuna saavan mobiililaajakaistaa
toimimaan. Päivittämällä uusi ydin proposed-updates -jakelusta alkaa
mobiililaajakaista taas toimimaan. Päivitystä varten pitää siis saada
nettiyhteys jotenkin muuten kuin mobiililaajakaistalla. Mokkulakäyttäjän
ehkä kannattaisi vielä välttää Ubuntu 9.10:n käyttämistä, mahdollisesti
jättää 9.10 väliin kokonaan ja siirtyä suoraan Ubuntun versioon 10.04.

Mokkuloiden ja nettitikkujen yhteensopivuustietoja löytyy
[Mokkulasulkeisista](http://www.siptune.net/tiki-index.php?page=MOKKULASULKEISET).

Nykyään Ubuntu 10.04:ssä ja uudemmissa Ubuntuissa mokkulat toimivat
usein suoraan. Jos ei toimi voi ekaksi kokeilla asentaa
**usb-modeswitch**. Jos se ei riitä, pitää
[Mokkulasulkeisista](http://www.siptune.net/tiki-index.php?page=MOKKULASULKEISET)
tai muualta etsiä miten se mokkula saadaan toimimaan. Järkevintä on
mokkulaa hankkiessa vaatia semmoinen malli joka toimii Linuxissa, ja jos
ei toimi vie kauppaan takaisin. Jos myyjä vieläkin väittää mokkulan
toimivan Linuxissa, vaaditaan ohje miten se saadaan toimimaan, tai
pyydetään myyjää pistämään se mokkula toimimaan jos se kerta on niin
helppoa.

### Tulostimet

Ennen tulostimen hankkimista kannattaa OpenPrinting.org:n
[tulostinluettelosta](http://www.openprinting.org/printer_list.cgi)
tarkistaa onko laite toiminut Linuxissa. Samasta paikasta joka
tulostimen kohdalla löytyy tieto parhaiten toimivasta ajurista.

Jos tulostin on niin uusi etteivät Linux-käyttäjät vielä ole päässeet
kokeilemaan, mahdollisesti valmistajan webbisivuilta ilmenee onko
Linuxiin saatavilla laiteajuri. Kannattaa suosia valmistajia jotka itse
tekevät tai teettävät Linux-ajurin.

### Porixi

Porissa toimii [Porin Linux-käyttäjien kerho](http://porixi.l-a.fi/) eli
Porixi, kerhon webbisivuilla on Linux- ja Ubuntu-asiaa ja tiedot kerhon
kuukausittaisista tapaamisista.

--Taleman 23. huhtikuuta 2008 kello 11.42 (EEST)
