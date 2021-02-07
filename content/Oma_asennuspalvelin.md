+++
Date = "2021-02-06T17:17:19.637Z"
Title = "Oma asennuspalvelin"
Description = "Oma asennuspalvelin"
Luokat = ["Linux alkeiskurssi"]
+++

Oma asennuspalvelin
-------------------

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

### debmirror

Oman Debian GNU/Linux asennuspalvelimen voi tehdä komennolla debmirror.
Se hakee netistä tarvittavat asennuspaketit ja kopioi ne
hakemistopuuhun, sieltä asennettavat koneet voivat hakea ne. Tällä
hetkellä i386-arkkitehtuurin asennuspaketit vievät yli 9Gt, kannattaa
varata noin 10Gt levytilaa ja laskea kuinka kauan tiedostojen nouto
kestää. debmirror-komennon voi ajaa tarvittaessa uudestaan, se osaa
noutaa vain muuttuneet asennuspaketit.

```
#!/bin/bash

date
debmirror /opt/Varasto1/mirror/debian --nosource --passive \
  --host=ftp.fi.debian.org --dist=etch --arch=i386 \
  --section=main,contrib,non-free --progress
date
echo "Loppui."
echo "Ehkä joudut ln -s dists hakemistossa tai "
echo "käyttämään samaa distron nimeä sources.list -tdostossa."
```

Hakemiston /opt/Varasto1/mirror/debian voi jakaa HTTP tai
FTP-yhteyskäytännöillä, tai antaa asennettavien koneiden liittää tuo
hakemisto. Siinä koneessa jonka levyllä tuo hakemisto on, voi hakemistoa
käyttää suoraan kirjoittamalla tiedostoon /etc/apt/sources.list
file:// -rivin.

Hakemiston jako HTTP-palvelimella on helppoa. Jos webserver on
asennettuna ja toimii, tarvitsee vain ln -s /op/Varasto1/mirror/debian
/var/www/debian ja tiedostot ovat noudettavissa. Kannattaa tarkistaa
selaimella osoitteesta <http://palvelin/debian> että tiedostot näkyvät.

**debmirror** noutaa tiedostot verkosta. Mikäli riittävän nopeaa tai
riittävän halpaa nettiyhteyttä ei ole käytettävissä, voi ostaa romput ja
kopioida niistä tiedostot asennuspalvelimelle. Täten tehtyä
hakemistopuuta voi päivittää **debmirror**:lla, se osaa noutaa
muuttuneet osat.

Debianin asennusromppuja voi käyttää suoraankin. Tällöin ohjelmapakettia
asennettaessa järjestelmä pyytää pistämään romppuasemaan sen rompun
jossa asennuspaketti on. Jokaiselle rompulle on yhden kerran tehtävä
**apt-cdrom add**, jolla rompun hakemiston tiedot luetaan järjestelmään.
Näiden tietojen avulla järjestelmä osaa pyytää oikean rompun asemaan.
Paljolta romppujen vaihtamiselta säästyy jos voi kopioida romput
kiintolevylle.

### approx

Koko Debian-jakelu on niin iso, ettei aina ole tarkoituksenmukaista
kopioida sitä kokonaan asennuspalvelimelle. Käyttämällä sovellusta
[approx](http://packages.debian.org/lenny/approx) saadaan
asennuspalvelimelle ne asennuspaketit joita käytetään. approx toimii
välimuistina, eli noutaa asennettavan paketin omaan hakemistoonsa ja
jakelee sieltä asiakaskoneille asennuspaketteja. Näin asennuspaketti on
asennuspalvelimen levyllä kunhan yksi asiakaskone on sen asentanut. Jos
koneita on paljon, saadaan merkittävää säästöä nettiyhteyden käytössä
kun asennuspaketit tarvitsee noutaa vain yhden kerran, ja asennus on
paljon nopeampaa koska lähiverkon nopeus tapaa olla moninkertainen
nettiyhteyden nopeuteen verrattuna.

Vuoden käytössä ollut approxia käyttävä asennuspalvelin viidelle
toimistokäytössä olevalle koneelle on kerännyt 799 Mt välimuistiinsa.
Koko Debianin jakelu on noin 10 Gt, eli levytilaa kuluu alle kymmenesosa
debmirroriin verrattuna. approx siivoaa kauan käyttämättä olleet
tiedostot pois välimuististaan, eli sen ei pitäisi kasvaa rajatta.

Approxin asennus kyselee enimmät tarpeelliset tiedot. Myöhemmin voi
säätöjä tehdä muokkaamalla tiedostoa **/etc/approx/approx.conf**.
Approxille on kerrottava missä asennuspaketit oikeasti ovat, jotta ne
saadaan noudettua ekan kerran. Kannattaa etsiä lähimmät
asennuspalvelimet ja kirjoittaa ne backends-määrityksiin lähin ensin.

```
;; Backend servers, in order of preference
backends =
        http://ftp.fi.debian.org/debian
        http://ftp.de.debian.org/debian
        http://ftp2.de.debian.org/debian
        ftp://ftp.uk.debian.org/debian

[security]
;; Debian security archive
backends =
        http://ftp2.de.debian.org/debian-security
        http://security.debian.org/debian-security

[ubuntu]
;; Ubuntu archive
backends = http://archive.ubuntu.com/ubuntu

[ubuntu-security]
;; Ubuntu security updates
backends = http://security.ubuntu.com/ubuntu
```

Approxille voi kertoa muutkin debian-pakettivarastot, jotta niidenkin
paketit tulevat välimuistiin. Debian-multimediasta löytyy flash,
realplayer, mplayer ja w32codecs.

```
[debian-multimedia]
; Debian Multimedia, Marillat et al
backends =
        http.//ftp.sunet.se/pub/os/Linux/distributions/debian-multimedia
        http://www.debian-multimedia.org
```

Asiakaskoneissa pitää tiedostossa **/etc/apt/sources.list** määrittää
asennuspalvelin ja portti 9999. Tähän tapaan:

```
deb http://palvelin:9999/debian/ etch main contrib
deb http://palvelin:9999/security etch/updates main contrib
```

Vastaavasti
muutkin jakelut, esimerkiksi Debian Multimedia.

```
deb http://palvelin:9999/debian-multimedia etch main
```
