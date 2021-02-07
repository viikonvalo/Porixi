+++
Date = "2021-02-06T17:17:09.176Z"
Title = "Kirjoitetaan webbisivu"
Description = "Kirjoitetaan webbisivu"
Luokat = ["Linux alkeiskurssi"]
+++

Kirjoitetaan webbisivu
----------------------

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

Kun on hankittu tietokone ja Internetti, tulee herkästi into tehdä oma
sivu Nettiin. Tämmöinen niin sanottu kotisivu on nykyään useilla
yrityksillä ja aika monella yksityishenkilölläkin. Ensin pitää keksiä
mitä sivulle kirjoittaisi, mutta sitten kun sisältö on selvillä voidaan
sivu tehdä erilaisilla tavoilla.

### Kirjoitetaan suoraan HTML:ää

Suoraviivaisin tapa webbisivuston tekoon on kirjoittaa HTML-koodia itse.
Jotkin teksturit osaavat jossain määrin HTML:ää eli valikosta löytyvat
merkkaukset tai merkkausten kirjoittamista on muilla tavoin helpotettu.
Alkuun pääsee ottamalla pohjaksi tyhjän webbisivun, kuten
[pohja.html](http://taleman.fi/pohja.html), ja lisäämällä tekstiä
body-merkkausten väliin.

Itse tehty HTML on hyvä tarkistuttaa oikean muotoiseksi, tässä auttaa
[HTML-validator](http://validator.w3.org/). Validatorin lomakkeelle
kirjoitetaan tarkistettavan sivun URL tai lähetetään tiedosto. Ohjelma
kertoo onko sivu määrittelyn mukaista HTML-merkkausta.

Kun Validator on tyytyväinen sivuun, pitäisi sivun näkyä kunnolla
kaikissa selaimissa. Jos ei näy, vika on selaimessa joka ei toimi
määrittelyn mukaisesti.

Tämä ei välttämättä ole helppo tapa, mutta jos löytää yksinkertaisen
sivun jonka ulkoasu miellyttää, saa nopeasti oman sivun muuttamalla vain
tekstit.

### Selaimen teksturi

Mozillassa on mukana Composer webbisivun kirjoittamiseen. Nykyään
sovelluksen nimenä on Seamonkey Composer, Debian GNU/Linuxissa nimenä on
Iceape Composer. Sovellus on sama, on vaan tullut uusi versio ja nimi
vaihtunut. Pienen sivun tekee Composerilla helposti.

### Webbisivueditori

Webbisivustojen tekoon tarkoitetut ohjelmat osaavat tehdä useasta
sivusta koostuvan sivuston, linkit sivujen välille tulevat
automaattisesti yms. tekemistä helpottavaa. Tunnettu sovellus on
[Kompozer](http://www.kompozer.net/) (ennen nimeltään NVU). Tämmöisten
sovellusten opettelu vaati jo vaivannäköä, ei ehkä kannata jos aikoo
vain yhden webbisivun elämänsä aikana tehdä.

Mikäli XML on tuttua, voi
[docbook-website](http://docbook.sourceforge.net/release/website/example/)
sopia sivuston tekoon. Sivut kirjoitetaan .xml-tiedostoihin, joista
layout.xml mukaisesti muodostetaan sivusto.
