+++
Date = "2021-02-06T17:17:35.156Z"
Title = "TeeItseKioskikone-Ubuntu"
Description = "TeeItseKioskikone-Ubuntu"
Luokat = []
+++

Ubuntu
======

{{< menuinclude file="/static/malline/TeeItseKioskikone-menu.md" >}}

Laite
-----

Ohjelmisto
----------

Ubuntu 8.04, päivitettynä päivän versioon.

Muokataan Firefoxin asetuksia siten, että selain unohtaa mahdollisimman
paljon istunnon aikana tehdystä kun istunto lopetetaan.

Muokkaa | Asetukset | Tietosuoja

-   Valitaan Tyhjennä valitut yksityisyystiedot aina kun Firefox
    suljetaan
-   Valinta pois kohdasta Kysy lupa tiedostojen poistamiseen
-   Yksityisyystiedot Asetukset, valitse kaikki poistettaviksi.

Muokkaa | Asetukset | Turvallisuus

-   Valinta pois kohdasta Tallenna sivustojen salasanat

R-Kiosk
-------

R-Kiosk on lisäosa Firefoxiin, tarkoitus on tehdä kioskiselain.
Asennetaan [R-Kiosk](https://addons.mozilla.org/fi/firefox/addon/1659).
R-Kiosk löytyy myös etsimällä kaikkien lisäosien joukosta Firefoxin
valikossa Työkalut | Lisäosat.

Työkalut | Lisäosat | Hae lisäosia

-   Etsitään ohjelma R-Kiosk ja valitaan Asenna Firefoxiin. Firefox
    pitää käynnistää uudelleen jotta R-Kiosk tulee käyttöön. Koska
    R-Kiosk poistaa käytöstä Firefoxin valikkoja, myös Muokkaa-valikon,
    ei normaalisti pääse Firefoxin asetuksia muokkaamaan eikä R-Kioskia
    poistamaan. Käynnistämällä Firefox tarkentimella --safe-mode otetaan
    tilapäisesti pois käytöstä lisäosat, myös R-Kiosk, ja päästään
    asetuksia säätämään tavanomaiseen tapaan. Kirjoita siis päätteeseen
    seuraava komento:

/usr/bin/firefox --safe-mode

R-Kiosk on oletusasennuksena vähän liiankin hyvä, selain on tosiaan
kokoruututilassa eikä valikoita näy. Harmittavasti myös osoiterivi
puuttuu, eli aloitussivulta ei pääse mihinkään jos ei sivulla satu
olemaan linkkejä muualle. Osoiterivin saa lisättyä ohjeella [More about
R-Kiosk](https://addons.mozilla.org/en-US/firefox/addon/1659), eli
muokkaamalla tiedostoa **user.js** hakemistossa
**\~/.mozilla/firefox/*<profiilin nimi>*/** (lisää tiedosto jos sitä ei
vielä ole). Tiedostoon kirjoitetaan user_pref("rkiosk.navbar", true);

Jos osoitepalkkia ei oteta käyttöön, pitäisi R-Kioskin aloitussivulle
kirjoittaa tarvittavat linkit ja jollain tavalla järjestää paluu
takaisin aloitussivulle (koska myös Takaisin-painikkeen on R-Kiosk
poistanut). Jos kaikki käyttäjät osaavat palata aloitussivulle
painamalla Alt-Home päästään vähällä. Helpompaa on lisätä R-Kioskiin
osoitepalkki, mutta silloin pääsee siirtymään mille sivulle vaan
osoitteen kirjoittamalla (tai etsimällä Google-laatikossa sivua). Kun
rkiosk.navbar on sallittu, on myös ikkunointiohjelman painikkeet mukana,
eli selaimen ikkunan voi pienentää ja sulkea.

Jos R-Kiosk:n navbar olisi hienosäädettävissä, eli voisi ottaa mukaan
vain painikkeet Päivitä, Takaisin, Eteenpäin ja Aloitus, olisi helpommin
tehtävissä halutulla tavalla rajoitettu selain. Käyttäjiä helpottaisi,
jos navbar olisi näkyvissä koko ajan. Nyt se tulee näkyviin kun
kohdistimen vie ruudun ylälaitaan, mutta mistäpä satunnainen käyttäjä
tätä tietäisi.

Arvio
-----

Tällä tavalla tehdyt kioskit olivat Pori Cupissa. Toimivat
odottamattoman hyvin, odotukset olivat matalalla kun tämä ratkaisu
jouduttiin äkkiseltään keksimään ja toteuttamaan kahdessa tunnissa kun
alkuperäinen suunnitelma ei sitten toiminutkaan. Yksi pulma oli, että
käyttäjät tykkäsivät sammuttaa selaimen, ja seuraava käyttäjä joutui
keksimään mistä selaimen sai takaisin. Pistettiin keskelle työpöytää
Firefoxin käynnistyskuvake, se aika hyvin auttoi.

Koska selaimessa oli osoitepalkki ja Googlen laatikko, pääsi mille
sivulle tahansa. Tästä ei suoranaista haittaa ollut, Veikkausliigan
sivuille mentiin paljon, siellä lienee jotain pelejä. Suosituin cupin
ulkoinen paikka olisi ollut IRC-Galleria, mutta Porin koulujen verkoista
on sinne pääsy estetty.

Tapio ja Ilkka
