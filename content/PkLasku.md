+++
Date = "2021-02-06T17:17:20.681Z"
Title = "Asenna PkLasku"
Description = "PkLasku"
Luokat = []
menu = ["teeitse"]
weight = 1000
+++

PkLasku nykyään MLInvoice
-------------------------

PkLasku on vaihtanut nimeään, tekijää ja toiminnallisuutta, se on
nykyään nimeltään MLInvoice. Yhä on suomalaista tekoa, saatavilla
[<http://labs.fi/mlinvoice.php>](http://labs.fi/mlinvoice.php). Tukea
löytyy
[keskustelualueelta](http://www.labs.fi/discussion/index.php?board=1.0).

PkLaskun asennus
----------------

[PkLasku-laskutusohjelmisto](http://pklasku.sourceforge.net/)
yksinkertainen, nopea ja varma ohjelma laskujen tekoon.

Asennuskertomus --Taleman 26. toukokuuta 2008 kello 15.24 (EEST)

Uusin versio 1.0.4 2008-05-13 (Sivu väittää uusimmaksi 1.0.2
<http://pklasku.sourceforge.net/order.php>)

### Tarvittavien sovellusten asennus

Asennan Debian versioon 4.0r3 eli Etch, peruskokoonpano johon
taskselillä lisätty www-palvelin ja tietokantapalvelin, sekä: aptitude
install openssh-server jed apache2 php5 mysql-server mysql-client
php5-mysql rcs

RCS ei ole pakollinen, pistin sen mukaan jotta voin versioida
asetustiedostoja. Teksturin jed tilalla voi olla oma mieliteksturisi.
Samalla tavalla toimii asennus Ubuntun versioon 8.04 eli Hardy Heron.

MySQL:n asennuksessa kysytään MySQL:n database administratorin
salasanaa, eli sen pääkäyttäjän salasanaa. Tämä pitää kirjoittaa
muistiin jotta jatkossa pääsee jotain MySQL:llä tekemään. Jos asennus ei
salasanaa kysynyt, salasana lienee tyhjä ja kannattaa vaihtaa tilalle
kunnollinen salasana (ja kirjoittaa se muistiin). [Miten MySQL:n
root-salasana
muutetaan](http://dev.mysql.com/doc/refman/5.0/en/resetting-permissions.html)

```
# mysqladmin -u root password KUNNOLLINENSALASANA
```

Jos jokin salasana on jo ennestään, sen voi vaihtaa (jos tietää
salasanan) komennolla

```
# mysqladmin -u root -p password KUNNOLLINENSALASANA
```

### Tehdään tietokanta

On tehtävä tietokanta nimeltä "pklasku". Jos asentaa **phpmyadminin**
(aptitude install phpmyadmin) voi tietokannan tehdä sillä. Heti
etusivulla on tietokannan teko.

Tiedosto CREATESQL on SQL-komentotiedosto joka tekee tietokantaan
tarvittavat taulut ja muutamia esimerkkitietueita. Siinä on kuitenkin
merkkijonoissa käytetty ISO 8859 -merkkejä, jotka näkyvät väärin
PKLaskun käyttöliittymässä kun siinä muuten käytetään UTF-8-merkistöä.
Eli kannattaa korjata CREATESQL:n merkistö, komennolla
```
mv CREATESQL CREATESQL.original
iconv --from-code=ISO-8859-15 --to-code=UTF-8 < CREATESQL.original > CREATESQL

wally:/var/www/pklasku\# file CREATESQL\*
CREATESQL:           UTF-8 Unicode text, with very long lines
CREATESQL.original:  ISO-8859 text, with very long lines
```

Edelleen tuodaan phpadminilla suoritettavaksi SQL-scripti CREATESQL.
Tämä tekee tietokantaan taulut, 12 kappaletta. Eli valitaan
tietokannaksi pklasku ja yläreunan valikosta **Tuonti** suoritetaan
CREATESQL-tiedosto. Kun tiedosto on browse-painikkeella löytynyt,
painetaan oikean alanurkan painiketta **Siirry** jotta komentotiedosto
suoritetaan.

Luodaan MySQL:ään käyttäjä pklasku, jolla oikeus käyttää tietokantaa
pklasku. Tämä jotta ei tarvitse MySQL:n pääkäyttäjän oikeuksia antaa
PKLaskulle. Voi käyttää phpmyadminia tai sql:n komentoriviä. Tuon
xxxxx:n kohdalle kirjoitetaan salasana.

```
GRANT DELETE,INSERT,SELECT,UPDATE ON \* TO pklasku@localhost IDENTIFIED BY "xxxxx"
```

Vastaavalla tavalla voi lisätä käyttäjiä, joilla oikeus käyttää
tietokantaa pklasku:

```
GRANT DELETE,INSERT,SELECT,UPDATE ON \* TO ilkka@localhost IDENTIFIED BY "xxxxx"
```

### Säädetään pklasku toimimaan

Puretaan PkLaskun asennustiedosto hakemistoon **/var/www/pklasku**.

Sitten roottina komentoriviltä palvelimen hakemistoon /var/www/pklasku

1.  Muokataan tiedostoon sqlfuncs.php mysql_connect -komentoon
    konenimi, käytäjätunnus, salasana. Älä pistä pklaskua käyttämään
    tietokantaa root-käyttäjänä.
2.  Vaihda hakemistopuun pklasku tiedostojen omistajaksi ja
    ryhmäomistajaksi www-data: **cd /var/www ; chown -R
    www-data:www-data pklasku**
3.  Vaihda oikeudet tiedostossa sqlfuncs.php jottei muut saa luettua
    sitä (koska salasana lukee siellä) **cd /var/www/pklasku ; chmod
    go-rx sqlfuncs.php**
4.  Debianissa pitää tiedostossa /etc/php5/apache2/php.ini poistaa
    kommenttimerkki riviltä **;extension=mysql.so** eli poistat
    puolipisteen rivin alusta. Sitten roottina **/etc/init.d/apache2
    restart**
5.  Nyt PKLasku toimii, mennään selaimella <http://konenimi/pklasku>.
    -   Kirjaudutaan sisään käyttäjänä admin, salasana on admin.
    -   Mennään PKLaskun käyttöliittymässä **System** | **Käyttäjät**
        ja klikataan vasemman reunan palkissa käyttäjää Administrator.
        Vaihda salasana joksikin muuksi.
    -   Jos tulee vaan virheilmoitusta "Call to undefined function
        mysql_connect()" olet jättänyt kohdan 4. tekemättä.
6.  Tee PKLaskuun varsinainen käyttäjä, jottei tarvi olla Administrator,
    eli **System** | **Käyttäjät** ja kliksautetaan **Uusi**. Valitse
    tyypiksi **Käyttäjä**, eli tavallinen käyttäjä. Administrator saa
    tehdä uusia käyttäjiä pklaskuun.
7.  Kirjaa Admin-käyttäjä ulos ja kirjaudu sisään luomanasi tavallisena
    käyttäjänä.
8.  **Asetukset** | **Yrityksen perustiedot**, kirjoita oman yrityksesi
    tiedot. Eli korjaa valmiina olevat tiedot tai poista esimerkkiyritys
    ja lisää oma yrityksesi.
9.  Opettele PKLaskun käyttöä, tee muutama asiakas (eli **Laskutus** |
    **Uusi asiakas**) ja ala laskuttamaan (eli **Laskutus** | **Uusi
    lasku**).
