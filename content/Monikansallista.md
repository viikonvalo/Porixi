+++
Date = "2021-02-06T17:17:17.546Z"
Title = "Monikansallista"
Description = "Monikansallista"
Luokat = []
menu = ["opiskelu"]
weight = 900
+++

Käyttöä useammalla kielellä
===========================

Joskus Linux-konetta käyttää monikielinen porukka, jolloin tarvitaan
kieliasetukset erilaisiksi joka käyttäjälle. Alla olevat ohjeet toimivat
ainakin Ubuntun versiossa 9.10.

Näppäimistöasettelu
-------------------

Näppäimistöasettelun voi vaihtaa lennossa lisäämällä Gnomen paneeliin
sovelman **Näppäimistön asettelu** (painetaan yläreunan paneelia
tyhjässä kohtaa hiiren ominaisuuspainikkeella, valitaan lisää paneeliin
ja etsitään sovelma luettelosta). Sovelma näyttää käytössä olevan
asettelun ja sillä voi lisätä asetteluita. Asetteluita voi olla enintään
neljä. Käytössä oleva asettelu vaihtuu sovelmaa hiirellä
kliksauttamalla.

Näppäimistöasettelun saa ikkunakohtaiseksi tai vaikuttamaan kaikkiin
ohjelmiin. Oletus on ikkunakohtainen asettelu.

Kieliasetukset
--------------

Gnomen yläpaneelin valikosta

```
Järjestelmä | Ylläpito | Kieliasetukset
```

valitaan halutut kielet. Kieli vaihtuu vasta seuraavalla
sisäänkirjautumiskerralla.

Kielen vaihtamisen jälkeen valikot, ohjelmien painikkeet ja suunnilleen
kaikki muukin teksti on valitulla kielellä (olettaen että kyseinen kohta
on sille kielelle käännetty). Samoin muutkin kieliriippuvat asiat.

Kannattaa olla nettiyhteys käytettävissä kieltä vaihdettaessa,
järjestelmä nimittäin noutaa ja asentaa valitun kielen tukeen
tarvittavat asennuspaketit jos ne puuttuvat.

Thunderbird ja Icedove
----------------------

Sähköpostin lukuun ja lähettämiseen tarjoitettu ohjelman Thunderbird
(joka Debian GNU/Linuxissa on nimellä Icedove) osaa näyttää sähköpostit
erilaisilla merkistökoodauksilla. Pitää ensin lisätä tarvitsemansa
koodaukset, esimerkiksi venäjän kielen käyttämä kyrillinen merkistö
lisätään näin:

```
Näytä | Merkistökoodaus | Lisää | Itäeurooppalainen | Kyrillinen (KOI-8-R)
```

Kun merkistökoodaus on valittu käyttöön ja saapuneessa sähköpostissa on
otsikkotiedoissa oikein merkitty viestin käyttämä merkistökoodaus, osaa
ohjelma valita itse sopivan merkistökoodauksen ja viesti näkyy oikein.
Merkistökoodauksen voi pakottaa viestikohtaisesti valitsemalla viestin
Näytä-valikon kautta halutun, esimerkiksi: Näytä | Merkistökoodaus |
Kyrillinen (KOI8-R)

Muut Linuxit
------------

Ubuntussa kielen ja näppäimistön voi valita myös
sisäänkirjautumisruudussa, tämä tapa toimii ainakin Gnomen
sisäänkirjautumisruudussa muissakin Linuxeissa. Valittavana on ne kielet
jotka on koneeseen asennettu.
