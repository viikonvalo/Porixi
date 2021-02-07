+++
Date = "2021-02-06T17:17:18.253Z"
Title = "Ohjeita luettavaksi"
Description = "Ohjeita luettavaksi"
Luokat = ["Kurssit","Linux_alkeiskurssi"]
+++

Ohjeita luettavaksi
-------------------

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

Ohjeita Debian GNU/Linux -järjestelmän käyttäjille löytyy asennetusta
järjestelmästä. Mikäli dwww on asennettuna voi suunnilleen kaikkien
asennettujen ohjelmien ohjeet lukea selaimella osoitteesta
[<http://localhost/dwww>](http://localhost/dwww).

![Selaimella voi lukea ohjeita jos dwww on asennettu](/images/dwww.png "Selaimella voi lukea ohjeita jos dwww on asennettu")

Komentojen käsikirjasivuja eli man-sivuja luetaan komennolla man tai
graafisella käyttöliittymällä xman. Joidenkin komentojen kohdalla
man-sivu on suppeahko ja täydellisempi ohje on luettavissa komennolla
info.

Asennettujen pakettien mukana tulleet ohjeet ovat hakemistossa
/usr/share/doc/paketin-nimi. Joskus ohjeisto on hyvinkin laaja, jolloin
ohjeet ovat yleensä omassa asennuspaketissaan.

Komentoriviltä käytettävissä komennoissa pitäisi kaikissa olla
sisäänrakennettu pikaohje, jonka saa näkyviin komentamalla komennon-nimi
--help tai komennon-nimi -h. Ohjelmissa joissa on graafinen
käyttöliittymä eli GUI tapaa olla oikeasta ylänurkasta löytyvä
sisäänrakennettu ohje. Joissain ohjelmissa ohjeen saa näkyviin
painamalla F1.

Debian GNU/Linux -projektin seittisivusto kokoaa myös ohjeita, ne
löytyvät osoitteesta
[<http://www.debian.org/doc>](http://www.debian.org/doc). Debianin
seittisivustolla on useita peilejä, kannattaa käyttää lähintä eli
Saksassa sijaitsevaa
[<http://www.de.debian.org/>](http://www.de.debian.org/).

[UNIX FAQ](http://www.faqs.org/faqs/unix-faq/faq/) on kiinnostava jos
haluaa perehtyä syvällisemmin Linuxin käyttöön, erityisesti käyttöön
komentoriviltä. Suomenkielinen suppeampi FAQ eli [useimmin kysytyt
kysymykset Linuxista](http://www.valot.fi/kalle/sal-faq/html/book1.html)
keskittyy Linuxiin.

Kirjastosta löytyy kirjoja, Debianissa on APT ja dpkg -komennot joita
muissa Linuxeissa tai Unixeissa ei ole, mutta muilta osin järjestelmän
ohjeiksi käyvät yleiset Linux- tai Unix-kirjat. Mikäli omasta
kirjahyllystä löytyy Unix-kirjallisuutta, se voi hyvinkin päteä
suurimmalta osaltaan myös Debianissa.

Tukea saa postituslistoilta tai IRC-kanavilta. On kohteliasta tutustua
ensin postituslistan usein kysyttyihin kysymyksiin, UKK eli FAQ, ja
selata postituslistan arkistoa jos sieltä jo löytyisi vastaus. Luettelo
Debianin postituslistoista on webbisivulla
[<http://lists.debian.org/>](http://lists.debian.org/), josta löytyvät
postituslistojen arkistot ja ohjeet listalle liittymiseen ja eroamiseen.

Suomenkielinen FTFM tietokanta on osoitteessa
[<http://ftfm.apz.fi/>](http://ftfm.apz.fi/). Debian Wiki on nykyään
virallisesti Debian-projektin osa. Wiki löytyy osoitteesta
[<http://wiki.debian.org/>](http://wiki.debian.org/). Kyseessä on
Wikipedia, eli "tietosanakirja" jota lukijat voivat täydentää. Myös
epävirallinen on [Debian User Forums](http://forums.debian.net/),
foorumi eli webbisivu, jossa kirjoitetaan kysymys ja toiset käyttäjät
toivottavasti vastaavat, tai sitten vaan keskustellaan.
[http://linux.fi/
Linux.fi-wiki](http://linux.fi/_Linux.fi-wiki "wikilink") on myös
Wikipedia, sinnekin tehdään talkoilla ohjeistusta.

Uutisryhmät eli newsit, virallisesti Usenet News ovat ehkä kätevämpiä
kuin webbiforumit. Omalla Internetpalveluntarjoajalla lienee
uutispalvelin josta seurattavat uutisryhmät voi lukea asiakasohjelmalla.
Mozillassa on Newsgroups-ikkuna, muita uutisten lukun sopivia ohjelmia
löytyy komennolla **apt-cache search news reader**. Sopiva uutisryhmä on
esimerkiksi sfnet.atk.linux.
