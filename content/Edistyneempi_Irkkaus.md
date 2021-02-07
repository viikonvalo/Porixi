+++
Date = "2021-02-06T17:17:04.036Z"
Title = "Edistyneempi Irkkaus"
Description = "Edistyneempi Irkkaus"
Luokat = []
+++

Edistyneempi irkkaus
====================

{{< menuinclude file="/static/malline/Irc-kurssimenu.md" >}}

Tavanomaiseen tapaan irkatessa jäävät näkymättä ne keskustelut jotka on
käyty kun on oltu kirjautuneena ulos. Tähän auttaa kone joka on aina
päällä ja johon asennetaan ohjelmat screen ja irssi. Irssin tilalla käy
muukin komentoikkunassa toimiva IRC-asiakasohjelma.

Koneeseen otetaan etäyhteys, SSH on oikein hyvä. Se lähettää
salakirjoitettuna yhteyttä muodostettaessa kirjoitettavat salasanat ja
salakirjoittaa myös yhteydellä liikuteltavan tiedon. Yhteyden
salakuuntelu ei siis hyödytä. Koneessa pitää olla SSH-palvelin ja
työasemakoneessa SSH-asiakasohjelma. SSH-asiakas taitaa kaikissa
Linuxeissa asentua automaattisesti, SSH-palvelimen joutuu ehkä
asentamaan.

Tarvittavat asennuspaketit siinä etäkoneessa ovat siis:

-   openssh-server
-   screen
-   irssi

Tee näin
--------

Avaa istunto työasemaltasi etäkoneeseen: ssh tunnus@etäkone.osoite
Käynnistä irssi screen-istunnon sisään: screen irssi Muodosta yhteys
IRC-verkkoihin ja liity kanaville kuten irssissä normaalistikin.

Edut
----

Se mikä tässä on hienoa, on mahdollisuus poistua istunnosta ja päästä
kuitenkin myöhemmin takaisin samaan irssi-istuntoon ja jatkaa siitä
mihin jäätiin. Jos kanavilla kirjoiteltiin sillä välin jotain, voi
vyöryttää ruutua takaisin ja lukea vanhat viestit. Näppäilemällä
Control-A Control-D poistutaan screen-istunnosta ja päästään takaisin
komentotulkkiin. Siinä voi tehdä tavanomaisia juttuja mitä
komentotulkissa nyt pystyy tekemään, ja screen-istunto ja irssi sen
sisällä toimivat koko ajan. Komentotulkista voi poistuakin tai kirjautua
kokonaan ulos, screen jää silti käyntiin.

Poistu screen/irssi -istunnosta siten että irssi jää pyörimään: /away
Poissaoloni syy
![kuva:Computer_key_Ctrl.png](/images/Computer_key_Ctrl.png "fig:size=30px")-![kuva:Computer_key_A_T.png](/images/Computer_key_A_T.png "fig:size=30px")
![kuva:Computer_key_Ctrl.png](/images/Computer_key_Ctrl.png "fig:size=30px")-![kuva:Computer_key_D_T.png](/images/Computer_key_D_T.png "fig:size=30px")

Sitten kun joskus myöhemmin kirjaudut takaisin, mahdollisesti toiselta
työasemalta kirjaudut taas <SSH:lla> koneeseen ja kirjoitat komennon:
screen -r -d

Tuolla komennolla pääsee takaisin screen-istuntoon. Jos istuntoja on
useita käynnissä, pitää ensin komentaa screen -ls jotta näkee istunnot,
ja sitten pitää valita joku niistä johon liitytään. Tarkennin -ls
näyttää istunnoista pid.tty.host (eli prosessin numero, päätteen
tunniste ja konenimi) sekä istunnon luontiajan. Jos arvasi väärän
istunnon, voi joko poistua siitä istunnosta ja valita toinen istunto
johon liitytään, tai lopettaa sen istunnon (sulkemalla irssi esimerkiksi
komentamalla **/quit**). Jos screen-istunnossa on käynnissä pelkkä
komentotulkki, sen voi lopettaa komennolla **exit**.

Lisäjippoja
-----------

Jos etäkone on jonkun kotona tavallisen ADSL- tai kaapelimodeemiyhteyden
päässä, sen osoite vaihtuilee silloin tällöin eikä sitä tavallisesti ole
nimipalvelussa. Pitää siis käyttää koneen IP-osoitetta, mutta sitä on
vaikea muistaa ja osoitteen muuttuessa pitää kaikille käyttäjille kertoa
uusi osoite.

Tässä auttaa dynaaminen DNS-palvelu, [dy.fi](http://dy.fi),
[dyndns.org](http://dyndns.org), tai [joku
muu](http://en.wikipedia.org/wiki/Dynamic_DNS) vastaava. Ensin
rekisteröidään sopiva nimi palveluun, nimen ensimmäinen osa pitää itse
keksiä ja loppuosa määräytyy valitun palvelun mukaan. Mahdollisesti
loppuosia on useita joista voi valita mieluisimman.

Kun rekisteröinti on tehty, asennetaan etäkoneeseen ohjelma joka
ylläpitää osoitetta, eli IP-osoitteen muuttuessa lähettää palveluun
muutostiedon ja rekisteröity nimi alkaakin viittaamaan uuteen
IP-numeroon.

Sopivia ohjelmia on esimerkiksi:

-   ez-ipupdate
-   ipcheck

--Taleman 24. marraskuuta 2009 kello 14.40 (UTC)
