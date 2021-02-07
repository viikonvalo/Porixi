+++
Date = "2021-02-06T17:17:17.906Z"
Title = "Monikulttuuri Ubuntu"
Description = "Monikulttuuri Ubuntu"
Luokat = []
menu = ["teeitse"]
weight = 700
+++

Monikulttuurinen Ubuntu
-----------------------

Tarvitaan Ubuntukone paikkaan jossa käyttäjät puhuvat useaa eri kieltä.
Tämä onnistuu asentamalla kielituki tarvittaville kielille ja tekemällä
käyttäjätunnus joka kielelle. Tämän käyttäjän asetukset, kieli
etunenässä, tehdään sopiviksi.

Asennetaan tavallinen Ubuntu 14.04 tai LUbuntu 14.04, toimivat samoin
paitsi asetukset löytyvät eri paikasta valikoista,
Järjestelmäasetuksista tai asetuksista.

### LibreOffice

Jos halutaan LibreOffice käyttöön, se tulee vakiona tavallisessa
Ubuntussa mutta Lubuntuun se on asennettava erikseen. Lubuntussa tulee
vakiona kevyemmät toimisto-ohjelmat. Asennetaan paketit libreoffice
libreoffice-help-ru libreoffice-help-en-gb libreoffice-help-fi
libreoffice-voikko

### Käyttöliittymä

Lubuntussa on käyttöliittymänä [LXDE](http://viikonvalo.fi/LXDE), se on
saman tapainen kuin Windows XP. Ubuntussa on käyttöliittymä
[Unity](http://en.wikipedia.org/wiki/Unity_%28user_interface%29), se on
erilainen kuin Windows, mutta peruskäyttö on helpohkoa. Voi asentaa
monta käyttöliittymää samaan koneeseen ja käyttäjäkohtaisesti valita
mitä käytetään. Valinta tehdään sisäänkirjautumisruudussa.

Näppäimistön asettelun voi valita käyttäjäkohtaisesti. Voi olla hämäävää
jos näppäinkuvat eivät vastaa käytössä olevaa asettelua, joten tätä ei
ehkä kannata vaihtaa. Käyttöliittymä näyttänee työkalupalkissa tai
vastaavassa mikä näppäinasettelu on käytössä, esimerkiksi FI, EN, RU
tms.. Se toimii myös painikkeena josta voi vaihtaa näppäinasettelun.

### Kieliasetukset

Lisää kielitukia asennetaan sovelluksella Kieliasetukset. Löytyy
Järjestelmäasetuksista tai Asetuksista. Painikkeella "Asenna tai poista
kieliä..." löytyy pitkä luettelo, josta ruksataan valituksi halutut
kielet. Jos asennuksessa valitsit Suomi, lienee suomenkielen tuki jo
valittuna samoin kuin englanti. Muut pitää etsiä listasta ja katsoa
niissä on valinta päällä. Odotetaan niiden asentumista, ja kun ollaan
takaisin Kieliasetusten pääikkunassa valitaan siitä "Toteuta
järjestelmänlaajuisesti", jotta kaikille käyttäjille ja
sisäänkirjautumisruudussa on kielituet tarjolla.

Kieliasetusten pääikkunassa voi raahata kielet haluamaansa
järjestykseen. Kun jossain sovelluksessa, esimerkiksi webbisivulla, on
useita kieliä tarjolla käydään kielien luetteloa läpi ylhäältä alas ja
valitaan ensimmäinen kieli joka tärppää. Kielen English alapuolella
olevia kieliä ei valita, eli jos sovellus ei osaa käyttää mitään muuta
kieltä se käyttää englantia. Järjestä siten, että Suomi on ylimmäisenä
ja English sen alapuolella. Pistä muut kielet englannin jälkeen, jottei
järjestelmä näytä järjestelmäviestejä esimerkiksi venäjäksi kyrillisillä
aakkosilla.

### Käyttäjätunnukset

Yksi käyttäjä on oltava pääkäyttäjä, jolla on kaikki oikeudet ja vain
salasanalla pääsee kirjautumaan. Ubuntun asennuksen tekemä pääkäyttäjä
on tällainen, pistä sille kunnollinen salasana. Muut käyttäjät tehdään
tavallisiksi käyttäjiksi, jotta niillä ei pääse liikaa sotkemaan
konetta.

Käyttäjätunnuksia tehdään sovelluksella "Käyttäjät ja ryhmät", löytyy
Järjestelmäasetuksista. Painikkeella "+" tai "Lisää" luodaan uusi
käyttäjätunnus. Mahdollisesti pitää ensin avata lukitus, jota varten
pitää tietää pääkäyttäjän salasana. Pistä käyttäjän nimeksi esimerkiksi
kielen nimi, kirjoitettuna sillä kielellä. Esimerkiksi suomi, English,
Русский, jne.. Käyttäjän nimi voi olla kirjoitettu kyrillisillä
aakkosilla, mutta käyttäjätunnus ei. Pistä siis käyttäjän nimi Русский
mutta käyttäjätunnus venaja.

Luo satunnainen salasana ja valitse "Älä kysy salasanaa
kirjauduttaessa". Näin käyttäjällä on salasana mutta sitä ei kysytä, eli
pääsee kirjautumaan sisään ilman salasanaa. Tarkista nämä käyttäjät
joilta ei kysytä salasanaa ovat tavallisia käyttäjiä, ei ylläpitäjiä.

Kirjaudu sisään käyttäjänä vaihtamaan kieliasetus. Pistä listan
ylimmäiseksi kieleksi se joka on tuolle käyttäjälle tarkoitettu. Tämä on
käyttäjän henkilökohtainen asetus, sen voi tehdä ilman pääkäyttäjän
salasanaa, koska asetus ei vaikuta muihin käyttäjiin. Asetuksen voi
tarkistaa seuraavalla sisäänkirjautumisella: valikoiden pitäisi olla
valitulla kielellä ja sovellusten samoin.

Jos teet asetuksen sellaiselle kielelle jota et osaa lukea, paina
etukäteen mieleen missä järjestyksessä valinnat ovat käynnistysvalikossa
ja uloskirjautumisruudussa, jotta osaat kirjautua ulos istunnosta.

Jos koneeseen on asennettuna useita työpöytäympäristöjä, voi
sisäänkirjautumisruudussa valita käyttäjäkohtaisesti mitä käytetään.
Tätä ei ehkä ole hyvä vaihtaa, koska toinen työpöytäympäristö eli
Desktop Environment voi olla hyvinkin erilainen käyttää, eli sitä ei
ehkä osaa käyttää.

### Muuta

Pistä unattended-upgrades asentamaan turvallisuuspäivitykset
automaattisesti. Näin ei koneen käyttäjille tarvitse antaa salasanoja
päivitysten tekemiseen. Jos pakettia ei ole asennettu, asenna se ja
komenna
```
apt-get install unattended-upgrades
dpkg-reconfigure unattended-upgrades
```
Vastaa Kyllä kysymykseen
asennetaanko vakaan version päivitykset automaattisesti.
