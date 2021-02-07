+++
Date = "2008-08-22T21:00:00.000Z"
Title = "Debian-esittely"
Description = "Debian-esittely"
Luokat = ["Tapahtumat","2008/08/23","Esittely"]
+++

Debian-projekti 15-vuotias
--------------------------

Porixi juhlistaa Debian-projektin 15-vuotista taivalta järjestämällä
Debian-esittelyn Porin Kauppahallissa 23. elokuuta kello 10 - 14.
Virallinen syntymäpäivä on 16. elokuuta, mutta esittely siis viikkoa
myöhemmin. Esitellään lähinnä seuraavia sovelluksia:

### Debian GNU/Linuxin asennin

Asennuksen pitäisi sujua noin 20 minuutissa, jonka jälkeen koneessa on
käyttöjärjestelmän lisäksi perussovellukset webbiselain, sähköposti,
toimisto-ohjelmat, musiikkisoitin, elokuvan katseluun sopiva sovellus
ym. Lisääkin sovelluksia on helppo asentaa.

### Perussovellukset

Toimisto-ohjelmat, kuvankäsittely, pikaviestin

### 64Studio

[64Studio](http://64studio.com/) on multimedian ja digitaalisen sisällön
tuottamiseen tarkoitettu Linux-jakelu. Se soveltuu esimerkiksi musiikin
ja äänen käsittelyyn ja tuottamiseen.

64Studio on jo lopetetun Agnula/Demudi Linux-jakelun jatkaja.
Agnula-projekti - A GNU/Linux Audio Project - aloitettiin Euroopan
Unionin rahoituksella. Tavoitteena projektilla oli tuoda
Linux-käyttäjien saataville vapaa audion ja graafisen tuotannon
Linux-jakelu.

Agnula-projektin päätyttyä koodin otti haltuunsa 64Studio, joka nimensä
mukaan oli erityisesti 64-bittisten PC - tietokoneiden käyttöä varten
kehitetty distribuutio. 64Studiosta on saatavilla myös 32-bittisille
PC:ille käännetty versio.

Demudin ja sittemmin 64Studion tärkeä kehitysperiaate on ollut
yhteensopivuus Debian GNU/Linuxin kanssa. 64Studio käyttää ohjelmien
asentamisessa ja hallinnassa Debianin apt-ohjelmaa. 64Studioon voi
liittää suoraan ohjelmalähteiksi Debianin ohjelmavarastot, jotka
kattavat tällä hetkellä 18 733 nimikettä. Debianin turvapäivitykset ovat
suoraan yhteensopivia 64Studion kanssa.

64Studion asentaminen tapahtuu Debianin vanhalla, tekstipohjaisella
asennusohjelmalla, joka Debiania aiemmin käyttäneille on tuttu.
64Studion asentamisen aikana ei valita erillisiä ohjelmakokonaisuuksia.
64Studion asennus vie kiintolevytilaa noin 2 - 3 Gt.

Audiokäyttöä varten 64Studion kerneliin sisältyvät reaaliaikaista
suorituskykyä parantavat kernelin muutokset, kts. [Real Time Kernel
Linux](http://rt.wiki.kernel.org/index.php/Frequently_Asked_Questions).
64Studio ei sisällä uusinta audiopalvelinta
[Pulseaudio](http://www.pulseaudio.org/), koska sen ominaisuuksista
reaaliaikaisessa audion tallentamisessa ei ole vielä tarpeeksi
kokemuksia. 64Studio käyttää sen sijaan [Jackd](http://jackaudio.org/) -
audiosysteemiä, joka on yhteensopiva
[ALSA](http://www.alsa-project.org/main/index.php/Main_Page):n kanssa.

Muita audiokäyttöön suunnattuja Linux - jakeluja:

[Ubuntu Studio](http://ubuntustudio.org/)

[Fedora](http://ccrma.stanford.edu/planetccrma/software/)

[Dynebolic](http://dynebolic.org/)


