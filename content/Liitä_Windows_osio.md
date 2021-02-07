+++
Date = "2021-02-06T17:17:11.275Z"
Title = "Liitä Windows osio"
Description = "Liitä Windows osio"
Luokat = []
menu = ["teeitse"]
weight = 400
+++

Liitä Windows-osio
==================

Windowsin käyttämissä levyosiossa on tiedostojärjestelmänä FAT tai NTFS.
Linux osaa lukea ja kirjoittaa näitä tiedostojärjestelmiä ja käyttö
onnistuu, kunhan liittäminen eli mount tehdään oikein. Windows NT:ssä ja
sen jälkeen julkaistuissa Windowseissa on tullut tuki pitkille
tiedostonimille ja Unicodelle. \[1\] \[2\]

Siirryttäessä Windowsin käytöstä Linuxiin, on kätevää jos voi antaa
Windowsin tiedostojen olla Windows-levyllä, ja käyttää samoja tiedostoja
Linuxistakin. Jos koneeseen on asennettu kaksoiskäynnistyksellä Linux
Windowsin rinnalle, voidaan Windowsin levyosiot liittää näkymään
Linuxissa. Tiedostoja voi yhä käyttää myös Windowsista, esimerkiksi jos
tarvitaan sovellusta joka on saatavilla vain Windowsille.

Liitosvalitsimet
----------------

### VFAT

VFAT-tiedostojärjestelmä liitetään valitsimilla `iocharset=utf8` ja
`umask=000`. Näin tiedostojen nimissä olevat merkit näkyvät oikein, eli
Unicode-merkkeinä. Muuten esimerkiksi äöÄÖ näkyvät kahden merkin
ryppäänä joita sovellukset eivät välttämättä osaa käsitellä ja
tiedostojen avaaminen ei onnistu. Ei kannata korjailla tiedostojen
nimiä, vaan käyttää oikeata valitsinta liitettäessä. Umask taas
tarvitaan, jotta tiedostoihin saadaan kirjoitusoikeus. \[3\]

Tiedostoon `/etc/fstab` kirjoitettaisiin

```
# Windowsin C: -levy
/dev/sda4   /media/C  vfat	user,defaults,auto,iocharset=utf8,umask=000	1	2
```

### NTFS

Liitettäessä NTFS-tiedostojärjestelmä käytetään liitosvalitsimia
`nls=utf8` ja `umask=0222`. Tiedostoon `/etc/fstab` kirjoitettaisiin

```
/dev/sda4 /media/C ntfs user,defaults,auto,nls=utf8,umask=0222 1 2
```

Lisää liitosvalitsimia on `mount`-komennon man-sivulla. Esimerkiksi
DOS-tekstitiedostojen rivinloppumerkin `CR LF` saa Linuxissa näkymään
Linuxin merkinnällä `LF`, mutta tämä automaattinen muunnos saattaa
sotkea joitakin ohjelmia, käytä sitä vain jos tiedät mitä teet.
Tekstitiedostot voi muuttaa komennoilla `dos2unix` ja `unix2dos`,
saatavilla asennuspaketista tofrodos \[4\]. Tämä siis koskee vain
tekstitiedostoja, esimerkiksi toimisto-ohjelmien tekemät tiedostot ovat
omassa tallennusmuodossaan eikä niissä pidä mennä muuttamaan
rivinloppumerkkejä.

NTFSProgs 2.0.0 julkistettiin 2007-09-29 ja mukana oli tuki
tiedostojärjestelmän lukemiseen ja kirjoittamiseen \[5\]. Tuon jälkeen
julkistetuissa Linux-jakeluissa lienee NTFS-tiedostojärjestelmän
kirjoitustuki mukana. Jos haluaa pelata varman päälle, kannattaa
Linuxissa kirjoittaa vain VFAT-tiedostojärjestelmään ja välttää
NTFS-tiedostojärjestelmälle kirjoittamista.

### Linuxiin kopioidut tiedostot

Jos tiedostot eivät olekaan Windowsin levyosiolla, vaan ne on kopioitu
Linuxin levylle, voi tiedostojen nimien merkistösotkut korjata
ohjelmalla `convmv`, saatavilla saman nimisestä asennuspaketista.
Komento on hieman hankala käyttää, on tarpeen lukea komennon man-sivu.
Komento ei vakiona oikeasti tee mitään, vasta tarkentimella `--notest`
käytettynä se kirjoittaa muutokset levylle.

Kannattaa kokeilla ohjelmaa tarkentimella `-i` eli interaktiivinen
toimintatila, jolloin ohjelma jokaisen tiedostonimen kohdalla näyttää
mitä tekisi ja antaa valita tehdäänkö vai jätetään ennalleen.

Huomaa, *ettei pidä käyttää `convmv`:tä* jos merkistösotkuiset
tiedostojen nimet ovat *windowsista liitetyllä levyllä*. Tällöin pitää
aiemmin kuvatuilla tavoilla liittää tiedostojärjestelmä oikeillä
liitosvalitsimilla jotta nimet näkyvät oikein. Jos kuitenkin menet ja
annat `convmv`:n muuttaa tiedostojen nimiä tässä tapauksessa, ne ovat
sitten sotkussa myös Windowsin puolella.

Huomaa myös, ettei `convmv` muuta tiedostojen sisältöä. Vain tiedostojen
nimiä muutetaan merkistöstä toiseen. Jos tiedostojen sisältöäkin pitää
muuttaa, sopivia sovelluksia ovat esimerkiksi `iconv` ja `recode`
merkistöjen muuttamiseen ja aiemmin mainitut `dos2unix` ja `unix2dos`
rivinloppujen korjaamiseen.

Linux-osion liittäminen
=======================

Tästä on oma [http://porixi.l-a.fi/Levyn_lisäys\#Liittäminen_bootissa
lukunsa](http://porixi.l-a.fi/Levyn_lisäys#Liittäminen_bootissa_lukunsa "wikilink")
tämän wikin sivulla [Levyn_lisäys](Levyn_lisäys "wikilink").

Viiteluettelo
=============

1. [<http://fi.wikipedia.org/wiki/FAT>](http://fi.wikipedia.org/wiki/FAT)
2. [http://fi.wikipedia.org/wiki/UTF-8\#Unicoden_käyttö](http://fi.wikipedia.org/wiki/UTF-8#Unicoden_käyttö)
3. [<http://www.cyberciti.biz/faq/mounting-windows-partition-onto-ubuntu-linux/>](http://www.cyberciti.biz/faq/mounting-windows-partition-onto-ubuntu-linux/)
4. [<http://www.thefreecountry.com/tofrodos/index.shtml>](http://www.thefreecountry.com/tofrodos/index.shtml)
5. [<http://www.linux-ntfs.org/doku.php>](http://www.linux-ntfs.org/doku.php)
