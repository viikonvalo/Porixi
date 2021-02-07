+++
Date = "2021-02-06T17:17:01.310Z"
Title = "Asennusvertailu-Windows7"
Description = "Asennusvertailu-Windows7"
Luokat = []
+++

Windows 7
=========

{{< menuinclude file="/static/malline/Asennusvertailu-menu.md" >}}

Vaikuttaa tämä Windows 7 huomattavasti paremmalta kuin Vista. Oikeastaan
ihmettelee, miksi mitään Vistan kaltaista surkeaa tekelettä lainkaan
ruvettiin toimittamaan asiakkaille kun kunnollistakin käyttöjärjestelmää
osataan tehdä. Esimerkiksi Windows 7:ssa sisäänkirjautuminen kestää 10
sekuntia, eikä 5 minuuttia kuten Vistasssa.

Asennettiin Windows 7 Home Premium. Asennus ei ollut kovin vaikea,
lähinnä ihmetytti miten vanhat levyosiot saadaan poistettua (poisto oli
Asema-asetukset-toiminnoissa, ne vissiin oli piilotettu jottei tumpelo
asentaja vahingossa poistele levyosioita), eteneekö asennus lainkaan kun
monta minuuttia menee eikä mitään näkyvää tapahdu, ja miksi yhäkin
asennuksen aikana pitää bootata kolme kertaa.

Windows 7:n käyttöoikeussopimus pienellä präntillä saatu mahtumaan
myyntipakkauksen kanteen. Oleellinen sisältö kiteytyy kappaleen 4
viimeiseen virkkeeseen: Kaikki oikeudet, joita ei ole nimenomaisesti
myönnetty, pidätetään. Tämä siis tarkoittaa, että jos meinaa ostamallaan
Windows 7 Home Premiumilla jotain tehdä, pitäisi
käyttöoikeussopimuksesta löytää lupa siihen. Jos lupaa ei löydy, pitää
sitä työtä varten hankkia joku muu käyttöjärjestelmä tai ostaa
lisäkäyttöoikeuksia.

Seuraavat arvot saatiin Windowsin tehomittaustyökalulla:

|               |     |
|---------------|-----|
| Suoritin      | 4,8 |
| Muisti        | 5,3 |
| Grafiikka     | 3,2 |
| Peligrafiikka | 3,2 |
| E. Kiintolevy | 5,9 |

Tehomittaustyökalu löytyy Ohjauspaneelista, "Järjestelmä ja suojaus",
"Tarkista Windowsin järjestelmäluokitus". Kesti muuten taas viisi
minuuttia kun etsin mistä tuo löytyy.

Ajureita ei tarvinnut etsiä ja itse asentaa, näyttivät kaikki
oheislaitteet toimivan heti asennuksen valmistuttua. Näytön tarkkuuskin
oli oikea. 3D-kiihdytystä ei vielä kokeiltu. Asennus kulutti levytilla 8
Gt.

| Selain | Toimistoohjelmat | Sähköposti | Teksturi | Laskin | Grafiikka | Musasoitin  | Elokuvakatselin | CD-poltto | CD ripper   | PDF-katselin | Sähköposti |
|--------|------------------|------------|----------|--------|-----------|-------------|-----------------|-----------|-------------|--------------|------------|
| IE8    | Ei               | Ei         | Wordpad  | On     | Paint     | Mediaplayer | Mediaplayer     | On, nimi? | Mediaplayer | Ei           | Ei         |

Asennukseen meni noin 42 minuuttia, kun asennus katsottiin päättyneeksi
kun päivitykset oli asennettu ja päästy kirjautumaan sisään. Tarkemmin
25:22 kului asennukseen ensimmäiseen sisäänkirjautumiseen asti, ja 15:59
päivityksiin, kun päivitettiin Windows Updaten ilmoittamat 11 tärkeää
päivitystä ja NVidian näyttöajuri. Nettiyhteys oli 2M/512 K jolla ei
muuta käyttöä ollut päivityksen aikana. Ajurien asentamiseen ei katsota
kuluneen aikaa, koska ilmeisesti kaikki ajurit löytyivät asennusrompulta
tai ainakaan asennuksen aikana ei havaittu ajurien noutamista.

Päivitysten jälkeen käynnistykseen kuluu 51 sekuntia,
sisäänkirjautumiseen 15 sekuntia ja sammuttamiseen 17 sekuntia.

Ne sovellukset mitä koneessa on toimivat asianmukaisesti. Valokuvat sai
ladattua kamerasta.

Havaittuja puutteita
--------------------

Koneen BIOS-kello on maailmanajassa. W7:n aikavyöhykkeeksi asetettiin
Helsinki, mutta kello oli silti kaksi tuntia jäljessä kunnes nettiyhteys
otettiin käyttöön. Arvattavasti W7 kävi netistä katsomasssa kellonajan.

Laitehallinta ilmoitti infrapunalaitteen löytyvän ja toimivan, mutta
tiettävästi koneessa ei ole infrapunalaitetta.

Selaimeksi tuli IE8, eikä missään vaiheessa kysytty haluaako jonkun muun
selaimen. Tästä kai piti EU:ssa olla määräys että selaimen pitää olla
valittavissa. Ei kokeiltu voiko IE8:n poistaa. Firefox asennettiin
VALO-CD versio 4:stä, mutta ei laskettu Firefoxin asentamiseen kuluvaa
aikaa mukaan asennusaikaan.

[Youtube](http://www.youtube.com) ei toimi, koska Flash Playeriä ei ole.
Tämä nyt kokeen havaintona, koska kuule wintoosakäyttäjien väittävän
ettei wintoosaan tartte asentaa Flash Playeriä. Sama juttu Javan kanssa,
ei sitäkään Windowsissa ole ennen kuin asentaa.

Virustorjuntaa ei asennettu, se pitäisi vielä jostain hommata. Tätä
asennuskokeilua varten ei katsottu tarpeelliseksi asentaa
virustorjuntaa, sen asentaminen lisäisi asennusaikaa.
