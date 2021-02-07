+++
Date = "2021-02-06T17:17:11.620Z"
Title = "Linux alkeiskurssi"
Description = "Linux alkeiskurssi"
Luokat = ["Kurssit","Linux_alkeiskurssi"]
menu = ["opiskelu"]
weight = 300
+++

Linuxin opiskelua
-----------------

Tähän olisi tarkoitus kerätä opiskelumateriaalia Linuxista, Unixista ja
vapaista ohjelmista. Kelpaa ohjeet myös semmoisista vapaista ohjelmista
joita käytetään muissa käyttöjärjestelmissä kuin Linuxissa, esimerkiksi
GIMP ja Windows tai MediaWiki ja MacOS.

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

Linux alkeiskurssi
------------------

### Kurssin aloitus

Kurssilla opetellaan käyttämään Linux-käyttöjärjestelmää. Tällä
alkeiskurssilla käsitellään järjestelmän ylläpitoa vain vähän.
Jatkokurssilla opetetaan niitä asioita joiden tekemiseen tarvitaan
pääkäyttäjän salasana.

Ehdotuksia kurssilla käsiteltävistä asioista voi tehdä. Tai kirjoittaa
niitä itse tänne Wikiin.

#### Koneen käynnistys ja sisäänkirjautuminen

Kone käynnistetään virtanappulasta. Mikäli koneessa on monikäynnistys
odotetaan käynnistysvalikon näkymistä. Käynnistysvalikko voi olla
Linuxin tekemä, jolloin sen tekee GRUB. Vanhoissa Linuxeissa voi olla
LILO, jolloin pitää painaa Vaihtonäppäintä (eli Shift) kun näkyy
[Media:lilo-1.jpg](/images/Lilo-1.jpg "wikilink") ja valitaan haluttu
käyttöjärjestelmä valikosta
[Media:lilo-2.jpg](/images/Lilo-2.jpg "wikilink"). Jos tullaan suoraan
GRUB:n käynnistysvalikkoon valitaan siitä nuolinäppäimillä ylös ja alas
siirtymällä haluttu käyttöjärjestelmä, eli Debian GNU/Linux (ei
Recovery). Käynnistysvalikon voi tehdä myös Windowsin työkaluilla, mutta
Linux osaa lisätä muut käyttöjärjestelmät käynnistysvalikkoon
automaattisesti, windowsissa pitää muokata piilotiedostoja.

![GRUB käynnistysvalikko](/images/Grub-1.jpg "GRUB käynnistysvalikko")

![LILO boot](/images/Lilo-1.jpg "LILO boot")

![LILO käynnistysvalikko](/images/Lilo-2.jpg "LILO käynnistysvalikko")

Koska Linux ja muut Unixit ovat monen käyttäjän järjestelmiä, on
käyttäjän kirjauduttava järjestelmään omalla tunnuksellaan. Tällöin
kirjoitetaan käyttäjätunnus kohtaan Käyttäjätunnus: ja oma salasana
kohtaan Salasana:. Käytettäessä englanninkielistä ohjelmistoa kohdat
ovat Login: ja Password:.

Salasanaa ei pidä kertoa muille. Internetissä ei muitakaan yhteystietoja
kuten osoitetta, pankkitilin numeroa yms. pidä kertoa jos ei ole aivan
varmasti tunnistanut keskustelukumppania ja mieluiten ei silloinkaan.
Kannattaa käyttää salattuja yhteyksiä lähetettäessä luottamuksellista
tietoa.

Salasana vaihdetaan komentoikkunassa komennolla passwd, joka ensin kysyy
vanhan salasanan ja sitten uusi salasana pitää kirjoittaa kahteen
kertaan. Salasanat eivät tulostu ruudulle niitä kirjoitettaessa, jotta
olan yli katselijat eivät näe mikä salasana on.

Salasanan valinnassa auttaa Helsingin Yliopiston ohjeen kohta [Hyvä
salasana](http://www.cs.helsinki.fi/compfac/ohjeet/Luvat/salasanat.html).

Jos unohtaa salasanansa, voi pääkäyttäjä eli root komennolla passwd
tunnus vaihtaa uuden salasanan. Pääkäyttäjän ei tarvitse tietää vanhaa
salasanaa.

#### Uloskirjautuminen

Kun on kirjauduttu sisään pitää muistaa kirjautua myös ulos
[Media:kirjaudu_ulos.jpg](/images/Kirjaudu_ulos.jpg "wikilink"). Muuten
järjestelmän mielestä käyttäjä on yhä kirjautuneena sisään. Jos poistuu
työaseman äärestä jättäen istunnon auki, voi seuraava käyttäjä päästä
toisen käyttäjän tunnuksella ja oikeuksilla käyttämään tietokonetta.

![Kirjaudu ulos GNOME:sta](/images/Kirjaudu_ulos.jpg "Kirjaudu ulos GNOME:sta")

#### Koneen sammutus

Konetta *ei saa* sammuttaa suoraan virtakytkimestä. Ensin on
käyttöjärjestelmä ajettava alas, eli sopivaan tilaan sammutusta varten.
Tällöin tallennetaan levylle avoinna oleva tiedostot ja käynnissä olevat
sovellukset lopetetaan.

![Sammuta tietokone sisäänkirjautumisruudusta](/images/Sammutus-gdm.jpg "Sammuta tietokone sisäänkirjautumisruudusta")

Usein käyttöjärjestelmä osaa itse kytkeä koneesta virrat pois, jolloin
koneen sammuttamiseksi ei ole tarpeen itse koskea virtakytkimeen.

Mikäli järjestelmä ei osaa sammuttaa koneesta sähköjä, tulee ruutuun
teksti **power down** kun sähköt voi turvallisesti katkaista.
