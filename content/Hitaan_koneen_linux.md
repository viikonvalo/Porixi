+++
Date = "2021-02-06T17:17:06.447Z"
Title = "Hitaan koneen linux"
Description = "Hitaan koneen linux"
Luokat = []
+++

### Hitaan koneen Linux

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

Haluttaessa käyttää työpöytäympäristöä Gnome tai KDE, tarvitaan
mieluiten 256Mt keskusmuistia, 400MHz prosessori ja levytilaa 3,0Gt.
Hitaammassa koneessa on syytä käyttää kevyempiä ohjelmistoja.

Tämmöisessä niin sanotussa nuhapumpussa X Window kuormittaa konetta,
erityisesti muistin määrä on kriittinen resurssi. Debian GNU/Linux
asennin vaatii vähintään 32Mt muistia, mutta graafiset ohjelmat ovat
aika hitaita noin pienellä muistilla. Kone soveltuu vain kevyeen
työskentelyyn kuten verkkopankin käyttöön, sähköpostiin ja irkkaamiseen.
Jos ei tarvitse graafista käyttöliittymää, tämmöinen kone toimii oikein
hyvin valtaosalla ohjelmista. Kyllä Debianin saa toimimaan 32Mt
muistilla, 120MHz prosessorilla ja 1,3G levyllä, mutta käytännöllisempi
minimi olisi 64Mt, 200MHz. Levytilaa ei välttämättä tarvita enempää,
riippuu pitääkö asentaa paljon ohjelmia tai tuleeko paljon omia
tiedostoja.

Kevyen Debianin saa jättämällä työpöytäympäristön asentamatta. Kun on
asennettu peruskokoonpano, valitaan asennettaviksi vain tarvittavat
ohjelmapaketit.

Kevyt X Window saadaan esimerkiksi ikkunointiohjelmalla icewm. Tämä on
vielä suhteellisen käyttäjäystävällisen näköinen. Vielä kevyempi
vaihtoehto on icewm-lite, joka jättää tehtäväpalkin ja muuta turhaketta
pois.

Ilmeisesti kevyin selain on dillo, se on kooltaan vain murto-osa
Mozillasta ja toimii sutjakkaasti koneessa jossa Mozillan
käynnistäminenkin kestää minuutin. Kaikkein kevyin selain olisi links,
mutta se on vain tekstiselain, toimii pääteikkunassa eikä osaa näyttää
kuvia. Harmittavasti dillo ei kelpaa verkkopankkien käyttämiseen, siinä
ei vielä ole HTTPS-yhteyskäytäntöä. Jos pankkiasioita varten tarvitaan
selainta, nuhapumppuun voidaan asentaa Opera. Se on saatavilla
Debian-asennuspakettina, noudetaan QT Static -versio ja pääkäyttäjänä
asennetaan se komennolla

```
dpkg --install opera-static_7.54-20040803.1-qt_en_i386.deb
```

Nuhapumpussa ei kannata käyttää graafisia kirjautumisruutuja, eli kone
käynnistyy konsoliruutuun. X Window käynnistetään komennolla startx,
mutta ensin kannattaa tehdä sopiva \~/.xinitrc-tiedosto käynnistämään
halutut sovellukset ja ikkunointiohjelma.

```
#! /bin/bash
uxterm &
xclock &
xsetroot -solid midnightblue &
/usr/bin/icewm
```

Tiedosto .xinitrc talletetaan omaan kotihakemistoon, huomaa piste nimen
ensimmäisenä merkkinä. Tämä tekee tiedostosta piilotiedoston joka ei näy
hakemistolistauksessa. Komennon ls valitsimella -a saa piilotiedostotkin
näkymään.

Tiedostossa on oleellista pistää &-merkki komentojen jälkeen, paitsi
viimeisellä rivillä. & käynnistää komennon taustalle, muuten suoritus
jäisi odottamaan ohjelman loppumista ennen kuin seuraavan rivin komento
käynnistetään. Viimeisellä rivillä taas on ikkunointiohjelman
käynnistys, siinä halutaankin X-istunnon päättyvän kun ikkunointiohjelma
sammutetaan kirjautumalla ulos.

IceWM tekee näytön alareunaan tehtäväpalkin. Haluamilleen ohjelmille voi
tehdä pikanäynnistyspainikkeen muokkaamalla tiedostoa \~/.icewm/toolbar,
esimerkiksi tämmöiseksi:

```
# This is an example for IceWM's toolbar definition file.
#
#
prog XTerm xterm uxterm -ls
prog XChat xchat xchat
prog Dillo netscape dillo
```

Tässä toolbar-tiedostossa prog-rivit tekevät pikakäynnistyspainikkeen.
Ensin on teksti joka näytetään kun hiiren kohdistinta pidetään
painikkeen päällä, sitten on kuvaketiedoston nimi ja viimeisenä
käynnistettävä komento. Dillolle ei sattunut olemaan kuvaketta IceWM:n
mukana, pistin huvin vuoksi tilalle netscapen kuvakkeen. Jos
kuvaketiedostoa ei ole, IceWM kirjoittaa painikkeeseen tekstin.
