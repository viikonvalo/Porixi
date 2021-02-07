+++
Date = "2021-02-06T17:17:39.317Z"
Title = "Ubuntun päivitys"
Description = "Ubuntun päivitys"
Luokat = []
menu = ["tutkimus"]
weight = 300
+++

Koska päivitys Ubuntun omalla automaattisella systeemillä uuteen
versioon 10.04 kestää kolmisen tuntia, tutkin onko nopeampaa kopioida
talteen säilytettävät tiedot vanhasta asennuksesta ja asentaa uusi
Ubuntu päälle. Nimetään tämmöinen päivitystapa *uusioivaksi
asennukseksi*.

Työpöytäkoneessa tavanomaiseen tapaan tehty jakeluversion päivitys
kestää tuskastuttavan kauan kun asennettuja ohjelmapaketteja on paljon.
Palvelinkäytössä olevassa koneessa päivitys lienee nopeampi kun
asennettuja ohjelmiakin on vähemmän. Uusioiva asennus palvelinkoneessa
teettäisi työtä, kun kaikki palvelut pitäisi asentaa ja tehdä niiden
asetukset.

Tietojen keruuta
----------------

### Levyosiot

Kannattaa katsoa mitkä ovat levyosiot, varsinkin jos levyllä on muutakin
kuin Linuxin juuriosio ja swap. Mikäli /home -hakemistopuu on
erillisellä levyosiolla, se on mahdollista säilyttää ennallaan vaikka
toiseen osioon asentaa Linuxin, kunhan muistaa mikä levyosio oli mikäkin
ja menettelee oikein. Jos ei ole erillistä levyosiota
home-hakemistopuulle, on se **kopioitava talteen** ja **palautettava**
uusioivan asennuksen jälkeen. Kotihakemistot ovat tällöin juuriosiossa,
ja asennus tyhjentää sen.

Komennolla sudo fdisk -l näkee mitä levyjä on ja mitä levyosioita niillä
on. Jos levyjä on monta mutta aikoo koskea vain yhteen niistä, voi levyn
antaa parametrina jolloin näytetään vain yhden levyn tiedot: sudo fdisk
-l /dev/sda

Komennolla df -hT voi katsoa mikä tiedostojärjestelmä on milläkin
osiolla ja liitospisteen. Lisäksi näkee osion koon, käytetyn tilan ja
vapaan tilan.

Tässä tapauksessa oli

| Levyosio  | Käyttö     |
|-----------|------------|
| /dev/sda1 | Linux root |
| /dev/sda2 | swap       |
| /dev/sda3 | /home      |

### Käyttäjät

Tehdyt käyttäjätunnukset katoavat uusioivassa asennuksessa,
käyttäjätunnukset on siis luotava uudestaan asennuksen jälkeen.
Tarvittavat tiedot löytyvät hakemiston /etc tiedostoista passwd, shadow
ja group (myös tiedosto gshadow jos käytät ryhmille salasanoja). Nämä
kolme tiedostoa voi kopioida talteen erikseen, tai luottaa niiden
löytyvän hakemistopuun /etc varmuuskopiosta.

Tällä komennolla voi katsoa mitä tehtyjä käyttäjätunnuksia koneessa on:
sort -n --field-separator=: --key=3 /etc/passwd

Kolmas "kenttä", eli kaksoispisteillä erotettu osa, on numeerinen
käyttäjätunnus. Asennus tekee käyttäjätunnuksen numero 1000, muut tehdyt
tavallisten käyttäjien tunnukset on numeroitu siitä eteenpäin. Siispä
tunnukset 1001, 1002, 1003, ... pitäisi asennuksen jälkeen luoda
uudestaan, mieluiten samalla numerolla ja saman nimisiksi, tai kopioida
näitä käyttäjiä vastaavat rivit vanhoista **passwd** ja **shadow**
tiedostoista uusiin. Vastaavasti tiedosto **group**, sieltä pitää
kopioida käyttäjien ryhmäjäsenyydet.

Tiedostoihin **shadow** ja **gshadow** ei ole lukuoikeutta muilla kuin
pääkäyttäjällä eli käyttäjällä root. Muidenkin tiedostojen kopiointi ja
palautus on parasta tehdä käyttäjänä root, jotta varmasti saa luettua
kaikki tiedostot ja pystyy palauttamaan ne säilyttäen tiedostojen
omistajat ja oikeudet. Oman kotihakemistonsa pystyy kopioimaan talteen
omalla käyttäjätunnuksellaan, mutta eipä juurikaan muita tiedostoja.

Tarkista ettei tiedostojen omistaja, ryhmäomistaja ja oikeudet muutu.
Jotkut palvelut kieltäytyvät toimimasta jos esimerkiksi tiedoston
/etc/shadow omistajat ja oikeudet ovat jotain muuta kuin

$ ls -lh /etc/shadow -rw-r----- 1 root shadow 1016 6.7. 16:19
/etc/shadow

Muista siis katsoa ennen kuin teet mitään mitkä omistajat ja oikeudet
ovat $ ls -lh /etc/shadow /etc/passwd /etc/group /etc/gshadow ja
tarkistaa etteivät ne muutu.

Käyttäjän työpöydästä voisi ottaa kuvakaappauksen talteen, voi sitten
uudessa järjestelmässä säätää saman näköiseksi.

Varmuuskopiot
-------------

Kopioin talteen /home, /root ja /etc -hakemistot. Ulkoiselle USB-levylle
kirjoitti noin 80 Gt tunnissa. Nopeus riippuu varmuuskopiolevyn ja
koneen omien levyjen nopeudesta, hitaampi määrää tahdin.

Otin talteen luettelon asennetuista ohjelmapaketeista, eli tämän
komennon tulosteen: dpkg --get-selections "\*" &gt; asennetut.txt

Tiedostossa `/etc/apt/sources.list` ja hakemistossa
`/etc/apt/sources.list.d/` on <APT:n> pakettilähteiden osoitteet. Nämä
voisi ottaa talteen jos pitää uudessa järjestelmässä saada samat
ylimääräiset pakettilähteet kuin aikaisemminkin.

Seuraavissa komennoissa pitäisi toimia rootin oikeuksilla. Jotta ei
tarvitse kirjoittaa sudo joka komennon eteen, kannattaa komentaa ensin
**sudo -i**. Tämän jälkeen siinä samassa pääteikkunassa toimitaan rootin
oikeuksilla, ja merkiksi siitä kehote muuttuu risuaitamerkiksi "\#".

Kopioin ulkoiselle USB-levylle, jossa oli FAT-tiedostojärjestelmä. Sinne
ei siis voi kirjoittaa tiedostoa jos sen koko on yli 4 Gt. Tämä oli
/home-hakemiston kohdalla rajoite, tar -tiedosto tyssäsi 4 Gt:n
kohdalla. Tiedostot voisi kopioida yksitellen, mutta
FAT-tiedostojärjestelmä ei osaa tallentaa tietoa tiedoston omistajasta
eikä oikeuksista. Nämä pitäisi sitten palautettaessa temppuilla jollain
sopivalla tavalla tiedostoihin takaisin.

Käytin siis tämmöistä komentoa jossa split jakaa ison .tar -tiedoston 1
Gt paloihin: tar --create --verbose --file=- ./home | ( cd /mnt/backup
; split --bytes=1G - tarfile- )

Tuosta saa koottua tar-tiedoston takaisin komennolla
`cd /mnt/backup ; cat tarfile* > /tmp/homebackup.tar`, kunhan tuo
hakemisto mihin .tar kirjoitetaan on semmoinen jossa ei ole tiedoston
maksimikoolle liian pieniä rajoja ja siinä tiedostojärjestelmässä on
tarpeeksi vapaata tilaa. Palautus toimisi myös suoraan komennolla
`cat tarfile* | ( cd / ; tar xpBf - )`, on kokeiltukin. Ei ollut
tarvetta palauttaa varmuuskopiolta, kun osasin olla kämmäämättä `/home`
-osion tiedostoja kadoksiin uusioivassa asennuksessa.

Muut hakemistopuut olivat pienempiä, tar-tiedosto oli pienempi kuin 4
Gt. Kopioin tähän tapaan: cd / tar cf /mnt/backup/etc.tar ./etc tar cf
/mnt/backup/root-home.tar ./root

Kannattaa huomata, että hakemistoa /etc **ei pidä palauttaa** uuteen
järjestemään. Katso vaan mallia siellä olevista tiedostoista kun teet
uudessa järjestelmässä sovelluksien asetuksia. Edes tiedostoa
/etc/passwd ei pidä kopioda uuteen järjestelmään, sieltä voi kopioida
vain muiden kuin järjestelmäkäyttäjien tunnuksia vastaavat rivit (eli ne
joilla käyttäjätunnus on &gt;= 1000).

Jos jossain muualla on tärkeitä tiedostoja, ne pitää muistaa ottaa
talteen. Jos on asennettu ohjelmia jostain muualta kuin käytetyn
Linux-jakelun pakettivarastoista, pitää ne asentaa uudestaan
Linux-jakelun päivityksen jälkeen joten niiden asentamiseen tarvittavat
tiedostotkin kannattanee kopioida talteen, tai joutuu noutamaan ne
uudestaan asennuksen jälkeen. Palvelinkoneessa voi olla tärkeitä lokeja
hakemistossa /var/log, tai palveluiden tallentamia tietoja
hakemistopuussa /var, esimerkiksi sähköposteja hakemistossa
/var/spool/mail/. Riippuu palvelun luonteesta pitäisikö ne ottaa
talteen. Palvelinkoneessa uusioiva asennus ei ole niin hyvä ajatus, voi
olla yksinkertaisempaa ja vaivattomampaa päivittää tavanomaiseen tapaan.

Kun varmuuskopiot on otettu, kannattaa taltio irroittaa päivityksen
ajaksi, jottei vahingossa asenna varmuuskopiolevylle. Ulkoinen USB-levy
on kätevä, se on helppo irroittaa.

Uusi asennus
------------

Uusi asennus on kätevää tehdä CD:ltä tai USB-muistitikulta. Uusissa
koneissa tuntuu olevan yleistä mahdollisuus valita käynnistyslaite.
Samassa kohtaa missä voi mennä BIOS:n asetuksia muokkaamaan on ehkä F11
tai F12 näppäimen painalluksella pääsy käynnistyslaitteen valintaan.
Tämä on kätevää, voi pitää BIOS:n asetuksissa käynnistyksen vain
kiintolevyltä ja valita tilapäisesti toinen käynnistyslaite jos
tarvitaan. Näin ei tule vahingossa käynnistettyä asemaan unohtuneelta
CD-levyltä tai USB-muistitikulta.

Levyä osioitaessa pitää huomata jättää mahdollinen erillinen /home -osio
rauhaan. Voi vaikka asentimelle ilmoittaa ettei sitä käytetä. Linuxin
juuriosio ja swap tehdään vanhan asennuksen vastaavista, voi joko
poistaa osiot ja tehdä uudet, tai jos vanhat osiot ovat valmiiksi
sopivan kokoiset valitsee ne käyttöön ja formatoitavaksi ja
liitoskohdaksi / (swapille ei tule liitoskohtaa, käyttö on swap eli
sivutus).

### Kotihakemistojen liittäminen

Uusioivan asennuksen jälkeen levyosiolle home tehdään nimiö, eli label.
Riippuu tiedostojärjestelmästä millä komennolla nimiö tehdään, e2label
EXT-tiedostojärjestelmille ja reiserfstune --label= jos
tiedostojärjestelmä on Reiserfs. Muilla tiedostojärjestelmille joudut
itse tutkimaan miten nimiö tehdään. Nimiönä home on hyvä
kotihakemistojen osiolle. Sitten lisätään tiedostoon /etc/fstab rivi:

1.  Kotihakemistot

LABEL=home /home reiserfs defaults 0 2 Katsot tietenkin, että
kolmannessa sarakkeessa on se tiedostojärjestelmä joka osiolla on, tai
sitten avainsana auto.

Nimiötä käyttämällä ei tarvitse hankalasti kirjoitettavia levyosioiden
UUID-tunnuksia käyttää.

Kannattaa siirtää muualle se mitä asennin teki hakemistoon /home. Sitten
komennolla sudo mount /home saat vanhat kotihakemistot näkyviin ja
käytettäviksi.

Jos vanhat kotihakemistot katosivat uusioivassa asennuksessa,
palautetaan tiedostot ennen asennusta tehdyltä kopiolta.

### Käyttäjätunnukset takaisin

Asennin tekee vain yhden käyttätunnuksen, muut on luotava erikseen. Voi
*joko* luoda käyttäjät Järjestelmä | Ylläpito | Käyttäjät ja ryhmät
-toiminnolla *tai* kopioida vanhat tiedot vanhoista passwd, group ja
shadow tiedostoista.

Jos teet ensimmäisellä tavalla, koita saada käyttäjille samat nimet ja
samat numeeriset ID:t kuin ennenkin.

Jos teet jälkimmäisellä tavalla, kopioi vain kopioitavia tavallisia
käyttäjiä vastaavat rivit, älä järjestelmäkäyttäjien tietoja.
Tiedostossa group pitää kopioda ryhmien rivit vastaavasti.

Asetukset
---------

Käyttäjien tekemät asetukset ovat käyttäjien kotihakemistoissa, ja ne
pitäisi olla nyt palautettu ennalleen.

Järjestelmän asetuksia ehkä joutuu muuttamaan, kun uusi linux on
erilainen tai toimii hieman eri tavalla kuin vanha linux. Pitää tutkia
ja lukea julkaisumuistiota ja päivitysohjeita.

Jos aikaisemmin jouduit vaikkapa laiteajureita asentamaan muualta kuin
käyttämäsi Linuxin asennuspaketeista, nyt pitää luultavasti tehdä
samalla tavalla. Toivottavasti muistat miten aikoinaan niitä asensit.
Jos et muista, voi hakemiston /etc varmuuskopiosta koittaa katsoa mitkä
asetukset sovelluksilla oli ennen. Ohjelmat tapaavat tehdä asetuksensa
/etc-hakemistoon sovelluksen mukaan nimettyyn alihakemistoon tai
tiedostoon.

Työpöytäympäristö Gnome ei Ubuntu 10.04:ssä tunnu osaavan toimia
kunnolla jos käyttäjällä on alunperin vanhemmalla Ubuntu 8.04:llä tehdyt
asetukset kotihakemistossaan. Gnome ei osaa piirtää yläpalkkia oikean
näköiseksi. Tulos on jotain 8.04:n Gnomen ja 10.04:n Gnomen väliltä. En
ole keksinyt tämän korjaamiseen muuta tapaa kuin poistaa vanhat
asetukset ja tehdä ne uudestaan. Silloin yläpalkki ja muukin
työpöytäympäristö on 10.04:n mukainen. Kannattaa ensin katsoa mitä
sovelluksia on sijoitettu yläpalkkiin jotta muistaa mitä sinne tulee
lisätä sitten kun asetukset on tyhjennetty.

Asetukset saa nollattua kirjautumalla ulos ja poistamalla toisena
käyttäjänä tai konsolilta sisään kirjautuneena kotihakemistosta
tiedostot ja hakemistot **.gconf** **.gconfd** **.gnome** **.gnome2**
**.gnome2_private** **.gtkrc-\***.

Toinen tapa asetusten nollaamiseen, jota en vielä ole itse kokeillut, on
komennolla **gconftool-2 --recursive-unset /hakemisto/**. Sopiva
hakemisto pitää itse keksiä, esimerkiksi katsomalla mitä hakemisto on
komennolla **gconf-editor**. Kaikki gconfig asetukset saa nollattua
komennolla **gconftoool-2 --recursive-unset /**. Ehkä myös
**gconf-editor** auttaisi, mutten keksi mitä asetusta sillä pitäisi
muokata jotta saisi kunnollisen paneelin yläreunaan Gnomessa. (tämmöisiä
neuvoi muep kanavalla \#ubuntu-fi 2010-08-29.)

Päivitys
--------

Sitten kannattaa päivittää järjestelmä, joko update managerilla tai
komentamalla sudo apt-get update sudo apt-get safe-upgrade

Tämä täytyy tehdä, koska CD:ltä asennetussa järjestelmässä on
asennuspaketit CD:n julkaisupäivältä, sen jälkeen on voinut tulla
paljonkin päivityksiä.

Sovelluksien asennus
--------------------

Uusioivassa asennuksessa tulee asennettua vain ne ohjelmat mitä
linux-jakelu vakiona asentaa. Muut tarvittavat sovellukset pitää asentaa
erikseen. Tässä auttaa kerätyt tiedot, eli tiedosto asennetut.txt josta
näkee mitä asennuspaketteja oli vanhassa asennuksessa. Tai sitten alkaa
vaan käyttämään, ja asentaa sovelluksia sitä mukaa kun huomaa jotain
tarvitsevansa.

dpkg --set-selections &lt; asennetut.txt aptitude install

Voi myös katsoa mitä suositellaan asennettavaksi, vaikkapa tässä wikissä
sivulta [Linux työpöydällä](/Ubuntu_tutuksi#linux-työpöydällä).

Lopputulema
-----------

Ei tämäkään tapa järin nopea ole, mutta on kuitenkin nopeampi kuin
Ubuntun päivitys päivitystyökalulla. Aikaa kuluu suunnilleen se aika
mitä muutenkin asennuksessa menisi, plus mahdollisesti tarvittava
tiedostojen palautus varmuuskopiolta. Lisäksi välttyy päivityksen
aiheuttamilta sekoiluilta, niitä tuntuu olevan jonkun verran. Itse
asennus menee nopeasti, tässä tapauksessa noin 20 minuuttia.

Sitten menee aikaa kun CD:ltä asennettujen pakettien uudet versiot
noudetaan netistä. Tätä vaihetta voisi nopeuttaa jos tekee uusioivan
asennuksen tai päivityksen useaan koneeseen käyttämällä välimuistia,
netti proxy siis, näitä on squid tai approx. Purkkavirityksenä voi
ensimmäisestä asennetusta koneesta kopioida hakemistopuun
**/var/cache/apt** talteen, ja kopioida siitä muihin asennettaviin
koneisiin ennen kuin tekee **apt-get safe-upgrade**. Tällöin
asennuspaketteja ei tarvitse noutaa netistä.

Enemmän menee aikaa kun säätää multimediaa, selaimen lisäosia yms.
toimimaan. Tältä ehkä säästyisi päivittämällä päivitystyökalulla, mutta
voi olla vanha versio teki asioita eri tavalla ja joka tapauksessa
joutuisi säätämään ja varmistumaan toimivuudesta kokeilemalla.

Uusioivassa asennuksessa on vielä semmoinen hyvä puoli, että voi vaihtaa
Linux-jakelusta toiseen. Esimerkiksi Ubuntun päivitys osaa päivittää
vain seuraaviin Ubuntun versioihin, vastaava rajoitus lienee kaikissa
Linux-jakeluissa. Mutta uusioivan asennuksen voi tehdä mistä
Linux-jakelusta vaan Ubuntun versioon 10.04, ja omat tiedostot ja
asetukset säilyvät. Myös voi "päivittää" 32-bittisen asennuksen
64-bittiseen, käsittääkseni minkään Linuxin päivitysohjelma ei osaa
tämmöistä tehdä. Hankaluuksia on odotettavissa vain jos päivittää
semmoiseen jakeluun jossa on vanhemmat versiot sovelluksista.
Sovellukset ovat harvoin alaspäin yhteensopivia, eli vaihto vanhempaan
versioon joka ei osaa lukea uudemman version asetuksia eikä ehkä
tallennettujen tiedostojen tallennusmuotoakaan teettää lisätyötä.

Tätä ohjetta voi soveltaa myös muissa tilanteissa joissa kone vaihtuu
tai palauttaa varmuuskopioilta kaikki koneen tiedostot. Jos varmuuskopio
ei ole levyotos josta voi suoraan palauttaa toimivan boottaavan
kiintolevyn, voi asentaa perusjärjestelmän ja sitten tämän ohjeen tapaan
vanhan järjestelmän tiedot.
