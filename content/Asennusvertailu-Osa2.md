+++
Date = "2021-02-06T17:17:00.561Z"
Title = "Asennusvertailu-Osa2"
Description = "Asennusvertailu-Osa2"
Luokat = []
+++

Asennusvertailu ratsastaa jälleen
=================================

{{< menuinclude file="/static/malline/Asennusvertailu-menu.md" >}}

Uusi Ubuntu, uudet vertailut. Ubuntu 10.04:n kunniaksi verrattiin
asennusaikoja ja kaksinkertaistettiin koneen muisti. Nyt siis muistia 4
Gt, muuten sama kone. Asennettiin Ubuntu 10.04 Desktop i386 Finnish
Remix.

Asennus USB-muistitikulta vei **18 minuuttia 41 sekuntia**. Osa
nopeutuksesta on muistitikun ansiota, siltä sai tiedostot luettua
nopeammin kuin CD-levyltä. Vaikea sanoa asentuisiko 10.04 nopeammin kuin
9.10 samanlaiselta taltiolta kun nyt ei viitsinyt polttaa CD-levyä.
Mahdollinen nopeutus lienee kuitenkin vähäinen.

Päivitys kestää
---------------

Samalla tuli kokeiltua päivitystä versiosta 9.10 versioon 10.04 Desktop
i386 Finnish Remix. Ensin oli vaikeuksia, kun päivitysten hallinta
sotkeentui. Paljastui tämä olevan tunnettu vika: jos asennettuna on sekä
ubuntu-desktop että xubuntu-desktop -paketit, päivitys ei onnistu ([vika
numero
571743](https://bugs.launchpad.net/ubuntu/+source/update-manager/+bug/571743)).
Korjaus oli poistaa jompi kumpi desktopeista, sitten päivitys onnistui.

Päivitys toimi, mutta on niin julman hidas. Nopeammin pääsee kun kopioi
talteen /home-hakemistopuun ja käyttäjätunnusten tiedot eli hakemistosta
/etc tiedostot passwd, group ja shadow, ja palauttaa ne sitten uuteen
järjestelmään ([Ohjeet](/Ubuntun_päivitys "wikilink") miten menetellä).
Päivityksessä kului ensin **71 minuuttia 49 sekuntia** kunnes
päivitettävät paketit oli noudettu netistä (yhteysnopeus 2 Mbit/s) ja
sen jälkeen **116 minuuttia 40 sekuntia** kunnes päivitys oli valmis ja
sai käynnistettyä päivitetyn järjestelmän ja siinä selaimen käyntiin.
Yhteensä siis **3 tuntia 8 minuuttia 21 sekuntia**.
