+++
Date = "2021-02-06T17:17:13.741Z"
Title = "Linuxin asennuksesta"
Description = "Linuxin asennuksesta"
Luokat = ["Kurssit","Linux_alkeiskurssi"]
+++

Linuxin asennuksesta
--------------------

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

Linuxin asentaminen ei välttämättä ole sen hankalampaa kuin minkään
muunkaan käyttöjärjestelmän asentaminen. Pulmia tulee lähinnä erikoisten
tai liian uusien oheislaitteiden kanssa jos oheislaitteiden valmistajat
eivät itse tee laiteajureita Linuxille. Debian GNU/Linux asennusohjeen
liite
[Asennus-howto](http://www.de.debian.org/releases/etch/i386/apa.html.fi)
kannattaisi ainakin lukea (se on suomennettu). [Debian GNU/Linux
asennusohje](http://www.de.debian.org/releases/etch/i386/index.html.fi)
on varsin pitkä koska asennuksen voi tehdä eri tavoilla ja
erikoistapauksiakin on. Tämäkin ohje on suomeksi. Mikäli tietokone ei
ole tavallinen PC, eli i386-arkkitehtuuria, pitää oman koneensa
asennusohje valita [Debian GNU/Linux 4.0 --
Asennusopas](http://www.de.debian.org/releases/stable/installmanual)
-sivulta mieluisella kielellä ja sopivassa tiedostomuodossa.

Jos haluaa vähällä vaivalla kokeilla toimiiko Linux omassa
tietokoneessa, niin sanottu Live-CD on näppärä. Esimerkiksi
[Ubuntu](http://www.ubuntu.com/) on suosittu ja toimii läppäreissäkin
varsin hyvin. Alle 256 Mt:n muistilla ei kannata Ubuntua kokeilla.

Kannettavat tietokoneet eli läppärit ovat hieman hankalia
asennuskohteita, niissä on usein eksoottisia oheislaitteita ja
valmistajakohtaisia erikoisuuksia. Kannattaa tutkia [Linux on
Laptops](http://www.linux-laptop.net/):n sivuilta oman läppärin kohdalta
kokemuksia asennuksesta.

[Debian GNU/Linux](http://www.de.debian.org/), jota tällä kurssillakin
käytetään, on aiemmin ollut vaikeasti asennettavan jakelun maineessa.
Asennuksen vaikeudesta voi olla montaa mieltä, mutta uusi Debianin
asennin ainakin kyselee paljon vähemmän kuin aiemmin, siinä on mukana
laitteistotunnistusta ja levyosioiden teko automaattisesti. Debian
toimii luotettavasti, se on tärkeää.

Käytettäessä uutta asenninta noudetaan sopiva romppuotos [asentimen
kotisivulta](http://www.de.debian.org/releases/etch/debian-installer/)
ja kirjoitetaan se rompulle. Otokset ovat 110 Mtavua jos voidaan noutaa
varsinaiset asennuspaketit Internetistä. Asennettaessa ilman
nettiyhteyttä olevaan koneeseen kannattaa noutaa tai ostaa kaupasta
asennusromput.

Ohjeita asennusromppujen kirjoittamiseen rompulle löytyy
[BurningIsoHowto](https://help.ubuntu.com/community/BurningIsoHowto)-ohjeesta.

Debianin asennusromppujen myyjiä löytyy esimerkiksi [Debianin
CD-toimittajat](http://www.de.debian.org/CD/vendors/#fi) -sivulta.
Debian on vapaa käyttöjärjestelmä, mikä tarkoittaa muun muassa, että
sitä voi vapaasti kopioida itselleen ja kavereilleen, asennusromputkin
voi itse noutaa ja kirjoittaa tyhjälle aihiolle. Jos ei itse voi tai
viitsi polttaa romppuja voi ne ostaa valmiina. Debianin vapaus
tarkoittaa myös kaikkien ohjelmien lähdekoodinkin olevan saatavilla.
Lähdekoodit ovat paitsi noudettavissa netistä saatavilla myös rompulla,
mutta lähdekoodeja tavallinen käyttäjä todennäköisesti ei tarvitse, eli
ne voi jättää ostamatta ja noutamatta.

[Asennuksen eteneminen valokuvina](http://taleman.fi/Asennusgalleria)
auttaa hahmottamaan miten asennus tehdään. Varsinaisesti asennus on
jatkokurssin asioita, tällä kurssilla käsitellään asennusta kurssin
loppupuolella jos oppilaat haluavat. Oma-aloitteiset käyttäjät voivat
koittaa asentamista tosta vaan tai lukevat ensin [asennuksen
pikaohjeen](http://www.de.debian.org/releases/etch/i386/apa.html.fi) tai
[koko
asennuskäsikirjan](http://www.de.debian.org/releases/etch/i386/index.html.fi).
Nämä ohjeet ovat saatavilla suomeksi, englanniksi ja noin 40 muulle
kielelle.

Jos päättää heti ryhtyä Debian GNU/Linux asennukseen, on huomioitava tai
selvitettävä etukäteen:

-   Jos koneessa on ennestään jokin käyttöjärjestelmä (esimerkiksi
    Windows) ja se halutaan säilyttää, on levylle järjestettävä tyhjää
    tilaa Linuxille (noin 2 Gt - 5 Gt). Tyhjä tila tarkoittaa vapaata
    levytilaa joka ei ole missään levyosiossa. Asennin osaa tehdä
    kaksoiskäynnistyksen eli koneen käynnistyessä valitaan kumpi
    käyttöjärjestelmä käynnistyy.
-   Merkki ja malli näytönohjaimesta, äänikortista, verkkokortista ja
    hiirestä. Asennin tunnistaa verkkokortin ja hiiren useimmiten
    oikein, mutta varmuuden vuoksi ne voi selvittää etukäteen.
-   Näytön käsikirjasta katsotaan minkämoisia taajuuksia ja tarkkuuksia
    näyttö osaa käsitellä. Tietämällä näytönohjaimen ja näytön
    ominaisuudet, saa parhaan mahdollisen kuvan. Ilman näitä tietoja voi
    valita näytönohjaimen ajuriksi vesa ja näytön valitsemalla helpossa
    asennuksessa resoluution sekä virkistystaajuuden mukaan.
-   Jos ei asentimen kysymyksiä ymmärrä, annetaan mennä oletusarvolla.
-   Jos verkkoasetukset (eli IP-numero, gateway jne.) tehdään
    automaattisesti niin hyvä on, muuten pitää tietää IP-numero, verkon
    peite, oletusreititin ja nimipalvelimet.

### Asennus Windowsin rinnalle

Kun asennetaan Linux koneeseen jossa on jo Windows, ja halutaan
säilyttää Windows käytössä, pitää tehdä levylle tilaa Linuxia varten.
Debian GNU/Linux asennin osaa löytää Windows-asennuksen ja asettaa sen
vaihtoehdoksi käynnistysvalikkoon.

Levytilaa tarvitaan mieluiten yli 5Gt jos asennetaan työpöytäympäristö
Gnome tai KDE. Vähemmälläkin levyllä tulee toimeen jos jättää isot
ohjelmistot asentamatta. On muistettava laskea myös sivutusalueen
levytila, tälle swap-levylle varataan tyypillisesti kaksi kertaa
keskusmuistin määrä.

Jos windowsilla on monta levyosiota, voi mahdollisesti jonkun tai
joitakin niistä poistaa. Jos levyosioissa on tarpeellisia tiedostoja, ne
pitää siirtää niille windowsin levyosioille jotka säilytetään.

Jos Windowsilla on vain C:-levy, pitää siihen saada vapaata tilaa niin
paljon että Linux saadaan asennettua, ja työtilaa Windows-käyttöön.
Ensin kannattaa poistaa tarpeettomat tiedostot, jotta levytilaa
vapautuu. Kun vapaata levytilaa on Linuxin tarvitsema sekä Windosille
tarpeellinen työtila, käynnistetään Windowsin levyn eheytys. Tämä
siirtää windowsin kaikki tiedostot levyn alkuun, jolloin vapaa levytila
on yhtenäisenä palana levyosion lopussa.

Jos tiedostojärjestelmä on FAT, osaa ilmainen FIPS pienentää osion. Jos
tiedostojärjestelmä on NTFS, osaa GNU-projektin parted NTFS-osion koon
muuttamisen. Ubuntun, Debianin ja mahdollisesti muidenkin Linuxien
asennin osaa pienentää Windows-osiota jotta tulee tilaa Linuxille. FIPS
on muun muassa Debianin asennusrompuilla hakemistossa tools/. Kannattaa
lukea käyttöohjeet huolella ennen kuin ryhtyy levyosioiden kokoa
muuttamaan. Jos levyllä on tärkeitä tiedostoja, on syytä ottaa niistä
kopiot, huonolla tuurilla tiedostot häviävät levyosioita peukaloitaessa.

Kun levyllä on vapaata tilaa, siis tilaa joka ei kuulu mihinkään
levyosioon, voidaan Linuxin asennin käynnistää.

Minä teen kaikki levyosiot, myös Windowsin tarvitsemat, Linuxin
osiointityökaluilla. Opin kantapään kautta, kun Windows oli tehnyt
osionsa osittain Linuxin osioiden päälle ja sotki Linuxini
käyttökelvottomaksi. Jos Windowsin uudelleenasennus ei tunnu liian
työläältä, turvallisinta olisi

-   tyhjentää levy,
-   tehdä osiot Linuxin osiointityökalulla,
-   asentaa Windows ja
-   asentaa Linux.
