+++
Date = "2021-02-06T19:26:20.499Z"
Title = "Keskustelu Porixista:Apua"
Description = "Keskustelu Porixista:Apua"
Luokat = []
+++

Netti
-----

Tarkistetaan kaapelien olevan kunnolla paikoillaan: Jos
kortissa/kytkimessä/ADSL-boxissa on linkkivalo, tarkistetaan palaako se.
Jos ei pala, kaapeli on katki, irti tai jotain muuta vikaa. Korjaa tämä
vika ensiksi, jos linkkivalo ei pala turha touhuta muuta. Kaikissa
korteissa ei ole linkkivaloa tai se ei näy kotelon ulkopuolelle. Riittää
jos toisesta päästänä näkee linkkivalon, kyllä se yhteys sitten toimii.

ADSL-modeemissa ja kaapelimodeemissa on merkkivalo DSL. Jos se ei pala,
ei modeemi saa yhteyttä keskukseen. Vika voi olla johdossa, tai sitten
palveluntarjoajan verkko on nurin. Jos johto näyttää ehjältä ja on
kunnolla kiinni, voi kysellä naapureilta toimiiko heillä saman
palveluntarjoajan netti. Jos kaikilla on netti katki pitää soittaa
palveluntarjoajan vikailmoitusnumeroon. Tai odotella, ja toivoa jonkun
naapurin soittavan.

Usein tietokone noutaa verkkoasetukset automaattisesti. Komennolla sudo
ifconfig voi tarkistaa mitä asetuksia on tullut. Komenolla less
/var/log/syslog voi katsoa lokia koneen tekemisistä, siellä pitäisi olla
myös rivit verkkoasetusten noutamisesta. Jos ei ole perehtynyt
verkkoasetuksiin, kannattaa tulostaa paperille ifconfigin tuloste
silloin kun netti toimii tämän ohjeen liitteeksi, Siitä voi sitten
vertailla onko asetukset samanlaiset.

Komento netstat -r näyttää reititystaulun Katso default-riviltä
Gateway-sarakkeesta reitittimen IP-numero. Kokeile pingata sitä, eli
ping osoite. Jos reititin vastaa pingiin toimii yhteys ainakin
reitittimeen asti, vika on siis kauempana.

Tiedostossa /etc/resolv.conf on nimipalvelimen osoite. Pingaa sitäkin.
Jos nimipalvelin vastaa pingiin on aika kumma jos netti ei toimi,
kokeile uudestaan josko se olisi alkanutkin toimimaan. Pingaa vaikka
jotain konetta joka on aina käynnissä, vaikka oman palveluntarjoajasi
konetta tai konetta www.funet.fi.

Jos reititin vastasi pingiin mutta nimipalvelin ei, voi vika olla vain
nimipalvelimessa. Jos muistat jonkun koneen IP-numeron, esimerkiksi
www.funet.fi on 193.166.3.7, voit kokeilla pingata sitä. Jos se vastaa
pingiin, kokeille vaikka selaimella jos sekin toimisi IP-numerolla. Jos
toimi, niin netti sinänsä toimii mutta nimipalvelu ei osaa muuttaa nimiä
numeroiksi. Selvitä käytetäänkö sitä nimipalvelinta jota on tarkoitus
käyttää. Toimivan nimipalvelimen kanssa netti pitäisi alkaa toimimaan
normaalisti.

Kone ei käynnisty
-----------------

Tuleeko sähköä? Töpseli seinään, virtalähteen pääkatkaisija päälle.
Kokeile lampulla tms. samasta töpselistä tuleeko sähköä. Jos ei
vieläkään mitään elonnerkkiä tietokoneessa kun virtakatkaisijaa paiinaa,
on kyseessä laitevika. Virtalähde on ehkä rikkoontunut, ne vanhemmiten
saattavat sanoa sopimuksen irti. Erityisesti jos virtalähde kuumenee se
saattaa kärähtää ja särkyä. Kuumenemista edistää jos virtalähteen
tuuletin ei pyöri kunnolla tai virtalähteen sisällä on paljon pölyä
estämässä ilman kiertoa. Pöytäkoneisiin saa uuden virtalähteen kaupasta.

Jos koneen merkkivalot syttyvät, tuulettimet lähtee pyörimään ja levyt
käynnistyvät, pitäisi päästä ainakin BIOS:iin. Jos pääsee, tarkista
käynnistysasetukset eli miltä laitteelta tietokone yrittää bootata.
Tarkista onko levyke, romppu, USB-muisti tms. koneessa. Ota pois jos et
halua käynnistää niiltä.

Jos BIOS:n mukaan kone käynnistyy kiintolevyltä ja BIOS näyttää koneessa
olevan kiintolevy, pitäisi käynnistymän. Jos koneen sisällä näkyy
kiintolevy mutta BIOS ei löydä sitä, katso onko kiintolevyssä virtajohto
kunnolla kiinni ja samoin datakaapeli paikallaan. Katso onko myös
johtojen toinen pää jossain kiinni. Jos ei vieläkään käynnisty
kiintolevyltä, onko varma että levylle on asennettu käyttöjärjestelmä?

Levykin on voinut rikkoutua, ehkä voit kokeilla toisella levyllä?

Jos kone käynnistyy Live-rompulta tai muulta taltiolta, voi komennolla
root katsoa komennolla fdisk -l mitä levyjä koneessa on. Samalla näkee
mitä levyosioita levyllä on. Sitten voi kokeilla liittää levyltä osion,
komennolla mount -o ro /dev/hda1 /mnt. Näin voi ainakin kopioida talteen
tiedostot, jos ei muuta.

Mikäli levyn saa liitettyä ja tiedostot ovat levyllä tallessa, mutta ei
vaan käynnisty levyltä, on levyn pääkäynnistyslohko ehkä sekaisin. Sen
voi kirjoittaa uudestaa, GRUB ja LILO tekevät pääkäynnistyslohkoon sen
koodinpätkän jonka kone suorittaa ensimmäiseksi.


