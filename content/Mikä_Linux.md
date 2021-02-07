+++
Date = "2021-02-06T17:17:15.469Z"
Title = "Mikä Linux"
Description = "Mikä Linux"
Luokat = []
menu = ["teeitse"]
weight = 600
+++

Linux-jakeluita eli distribuutioita on useita kymmeniä, eli valinnan
varaa on liikaakin jos vaan haluaa vaivattomasti GNU/Linuxin.

Valintaa
--------

On vaikeaa sanoa mikä olisi paras Linux, ainakaan tietämättä
käyttötarkoitusta. Esimerkiksi palomuurikoneelle on varta vasten tehtyjä
pikkujakeluita, vaikkapa [IPCop](http://ipcop.org/), jolla ei ole
tarkoituskaan tehdä muuta kuin palomuuri. Tämmöinen muokattu pikkujakelu
lienee parempi juuri siihen käyttöön kuin yleisjakelu jolla voi tehdä
suunnilleen mitä vaan.

Debian ja Ubuntu
----------------

Debian-kehittäjän mielestä [Debian GNU/Linux](http://www.de.debian.org/)
on tietenkin paras. Debianissa on hyvää helppo päivitettävyys, sekä
tietoturvapäivitykset että päivitys seuraavaan versioon sujuvat
vaivattomasti ja Debian toimii luotettavasti (jos käyttää vakaata
jakelua, jos haluaa huonosti toimivan Linuxin Debian tarjoaa testattavan
ja epävakaan jakelun). Toiseksi paras olisi Debianiin pohjautuva
[Ubuntu](http://ubuntu.com/). Ubuntu ei toimi kaikilla Debianin
tukemilla prosessoriarkkitehtuureilla, mutta sen luvataan olevan
helpompi asentaa kuin Debian GNU/Linux ja saatavilla on myös Ubuntu Live
CD pikaisiin Linux-kokeiluihin.

Hitaan koneen Linux
-------------------

Ubuntu versio 8.04:n vähimmäisvaatimus Live-rompulta käytettäessä on 384
Mt keskusmuistia. Järjestelmän saa asennettua 256 Mt:n muistilla
asentamalla suoraan käynnistysvalikosta, siis käynnistämättä
Live-järjestelmää.

XUbuntu toimii 128 Mt:n muistillakin, mutta ei ole erityisen ripeä näin
niukalla muistilla.

### DSL

Erityisesti pieniin ja vanhoihin koneisiin tarkoitettu
[DSL](http://www.damnsmalllinux.org/) toimii varsin ripeästi hitaissakin
koneissa. Itse olen käyttänyt 120 Mhz Pentiumissa 64 Mt:n muistilla.
DSL:n vähimmäisvaatimuksiksi X Window:n kera ilmoitetaan 486 suoritin ja
24 Mt muistia. Jos muistia on 128 Mt tai enemmän, DSL:n voi kopioida
keskusmuistiin jolloin ohjelmien käynnistäminen on järkyttävän nopeaa.
DSL:n koko on vain 50 Mt, joten se mahtuu kätevästi USB-muistitikullekin
ja tilaa jää vielä omille tiedostoillekin.

DSL:llä on rajoituksiakin. Koska se on tarkoitettu vanhoihin koneisiin,
on ytimenä yhä Linux 2.4, joka on paljon pienempi kuin 2.6. Mutta
uusissa koneissa tarvittaisiin laiteajureita joita ei 2.4-ytimessä ole.
Erityisesti DSL ei osaa käyttää Sarja-ATA-levyjä. Samoin WLAN-tuki on
kehno. DSL:ää voi käyttää USB-muistilta vaikka koneessa olisikin
SATA-levyt, levyjä ei vaan pääse käyttämään eikä DSL:ää asentamaan
levylle.

DSL:n asentaminen USB-muistille sujuu helpoiten käynnistämällä DSL
rompulta ja etsimällä valikoista asennus USB pendrivelle.

Itselläni on DSL USB-muistitikulla (Kingston 1 Gt), sitä kun kuljettaa
mukanaan saa näppärästi Linuxin käyttöönsä melkein koneessa kuin
koneessa, kunhan kone vaan osaa käynnistyä USB-muistilta.

DSL:n voi asentaa kiintolevyllekin, sieltä käytettynä se on hieman
nopeampi kuin USB-muistilta (oma kokemukseni, vaikuttaa varmaan se, että
niissä vanhoissa koneissa joissa olen käyttänyt on ollut vain USB
1.x-liitäntä, joka on paljon hitaampi kuin USB 2.0). Kiintolevylle
asennettuun DSL:ään voi asentaa lisää ohjelmapaketteja DSL:n omalla
pakettienhallintajärjestelmällä.

Yleiskäyttöisiä Linuxeja
------------------------

Muita yleiskäyttöisiä Linuxeja ja niiden asennusromput löytyvät
[Distrowatch.com](http://distrowatch.com/dwres.php?resource=major)
-sivulta.

Äänityöasema
------------

Äänityöasemaksi Linux on Windowsia parempi ytimen
reaaliaikaominaisuuksien ansiosta, äänen käsittelyssä ei ole
ylimääräistä viipettä. Porixin Linux-esittelyissä on kaksi kertaa
esitelty multimediajakelua [64Studio](http://64studio.com/). Siinä on
valmiina äänen käsittelyyn tarvittavat sovellukset ja reaaliaikaydin.
Äänityöasemakone kannattaa pitää erillisenä, eli ei asenneta siihen
toimisto-ohjelmia tai muuta ylimääräistä. Jos tietokoneita on vain yksi
käytössä, voi kaksoisasennuksella pistää rinnalle tavallisen
Linux-jakelun.

64Studio ja [Ubuntu Studio](http://ubuntustudio.org/) ovat kehittyviä
jakeluita. Multimediajakeluita joiden kehitys on lopetettu tai
keskeytyksissä ovat AGNULA ja MeMuDi.
[AGNULA](http://en.wikipedia.org/wiki/AGNULA) eli "A GNU/Linux Audio
distribution" on tehnyt Debianin ja Red Hatin pohjalta jakelun jossa
äänenkäsittelyyn sopivan ytimen lisäksi on koottuna liuta ohjelmia.
Debianiin pohjautuva on nimeltään DeMuDi ja toimii oikein hyvin.
Wikipedian mukaan AGNULA:n kehitys on loppunut mutta kehitystä jatkaa
[Debian Multimedia](http://wiki.debian.org/DebianMultimedia) -projekti.
Äänen käsittelyn ohjelmat ovat samat jotka tulevat Debianissakin,
DeMuDi:n varsinainen ero on sen reaaliaikaydin. Periaatteessa voi
itsekin kääntää vastaavan ytimen tavalliseen Debian-järjestelmään, mutta
jos aikoo tosissaan tehdä äänityöaseman, kannattaa jättää kaikki muu
tauhka pois.

Teknisen suunnittelun ohjelmistot
---------------------------------

Linux sopii erinomaisesti tekniseen suunniteluun. Tällä tarkoitetaan
CAD-piirtämistä (2D, 3D), mallintamista ja simuloimista. Linuxille
löytyy tähän tarkoitukseen niin vapaita kuin suljettuja ohjelmia. On
olemassa myös [CAElinux](CAElinux "wikilink"), jakelu johon on koottu
paljon laadukkaita tietokoneavusteisen suunnittelun vapaita ohjelmia.
