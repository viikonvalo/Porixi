Porixin verkkosivut
====================

Tämä repository sisältää Hugo-projektin Porixin verkkosivujen tekemiseen.

Asetukset
----------

Hugon asetustiedosto on `config.toml`, jossa määritellään sivuston otsikko,
käytettävä teema, sivuilla käytettävä taksonomia (tässä tapauksessa yksi "luokka")
sekä joitain kääntämisen yhteydessä käytettäviä parametreja.

Kun käännettävä Hugo-sivusto on oman domaininsa juuressa, perusosoitteeksi
sopii `baseurl = "/"` ja kannattaa käyttää muuttujaa `relativeURLs = true`.
Näillä asetuksilla Hugo generoi sivuston sisäiset linkit suhteellisina.

Sisältö
----------
Sivuston sivut löytyvät Markdown-muodossa hakemistosta `content`. Kunkin tiedoston
alussa on `+++`-riveillä eroteltu osio, "Front Matter", jossa määritellään sivun
otsikko, kuvaus, päivämäärä, luokat, joihin sivu kuuluu, mahdolliset aliakset
sivun osoitteelle (uudelleenohjauksia) sekä valikot, joissa sivun halutaan näkyvän.

Esimerkki:
```
+++
Date = "2021-02-06T17:17:08.150Z"
Title = "Kioskikone"
Description = "Kioskikone"
Luokat = ["ohje"]
menu = ["mainside"]
weight = 400
+++
```

Sivuilla käytetyt kuvat (ja muut linkitetyt tiedostot) ovat hakemistossa `content/images`.

Kuvia voi lisätä suoraan Markdown-komennolla:
```
![Title teksti](/images/kuva-tiedosto.png)
```
Toinen vaihtoehto kuvien lisäämiseen on Hugon sisäänrakennetulla "Shortcodella":
```
{{< figure src="/images/kuva-tiedosto.png" title="Otsikko" caption="Kuvateksti" >}}
```
Jälkimmäinen tapa luo kuvan ympärille `<figure>` ympäristön kuvateksteineen.
Lisää parametreja `figure` shortcodelle löytyy [Hugon dokumentaatiosta](https://gohugo.io/content-management/shortcodes/#figure).

Sivuston kuvien sekä sisäisten linkkien osoitteet kannattaa aloittaa
`/`-merkillä, jotta linkin polku menee oikein. Tämä johtuu siitä, että
käytössä on ns. "prettyURL"-asetus, eli sivut eivät pääty `.html`-päätteeseen.
Käytännössä siis kukin sivu on omassa alihakemistossaan nimellä `index.html`.
Jos esimerkiksi sivulla `porixi.l-a.fi/Tapaamiset/` oleva linkki olisi
muodossa `Raportti-2012-01-19`, niin sivua haettaisiin virheellisesti osoitteesta
`porixi.l-a.fi/Tapaamiset/Raportti-2012-01-19/`.

### Ohjelmakoodit

Jos sivu sisältää ohjelmakoodia tai komentorivitulosteita, niiden alku ja loppu
voidaan merkitä Markdownissa riveillä, joilla on kolme "backtick"-merkkiä.
Koodille tulee automaattisesti syntaksikorostukset, jos kieli tunnistetaan oikein.
Muussa tapauksessa käytetyn kielen voi kirjoittaa "backtick"-merkkien perään.

### Pikavalikot

Esimerkiksi kurssisivut liittyvät toisiinsa ja niillä on sivun oikeassa
yläkulmassa sivujen välillä linkittävä pikavalikko. Valikot on nyt toteutettu
niin, että niiden sisällöt ovat Markdown-tiedostoina hakemistossa `static/malline/`
ja ne sisällytetään sivulle lyhytkoodilla (shortcode) `menuinclude`. Esimerkiksi:

```
{{< menuinclude file="/static/malline/Asennuksista-menu.md" >}}
```


Valikot
---------

Yläreunan pikalinkkilista on nimeltää `main` ja siinä näkyvät ne sivut, joiden
"Front Matter" sisältää `menu`-listassa arvon `main`.

Samalla tavalla vasemman reunan valikoiden nimet ovat `mainside`, `tutkimus`,
`opiskelu` ja `teeitse`. Sivu voidaan lisätä näihin valikoihin lisäämällä valikon
nimi sivun "Front Matterin" `menu`-listaan. Valikoiden alkioiden järjestys
määräytyy käytetystä `weight`-muuttujan arvosta. "Kevyemmät" ensin.

Ylävalikon määrittely on teemassa sivupohjan muiden alkuosien kanssa tiedostossa:
`themes/porixi/layouts/partials/header.html`.

Vasemman sivuvalikon määrittely on puolestaan tiedostossa:
`themes/porixi/layouts/partials/side-menu.html`. Tätä tiedostoa voi muokata,
jos haluaa lisätä, poistaa tai järjestää vasemman valikon osia.


Teema
-------

Sivun rakenne, asettelu ja ulkoasu tulee hakemistossa `themes/porixi/` olevista
tiedostoista. Rakenne määritellään hakemistossa `themes/porixi/layouts/` sivupohjilla.
Etusivun rakenne tulee tiedostosta `themes/porixi/layouts/index.html` ja
muut sivut sivutyypeittäin alihakemistossa `_default` olevista pohjista.
(Käytössä lähinnä `single.html` ja `terms.html`.) Lisäksi näihin sisällytetään
yhteisiä sivujen osia, jotka ovat hakemistossa `partials`.
Osia ovat esimerkiksi "header", "footer", "toc-pages" ja "side-menu".

Ulkoasun tyylit määritellään tiedostossa `themes/porixi/static/css/styles.css`.
Tämän tiedoston alussa on määritelty css-muuttujina käytetyt värit niin, että
niitä on helppo muuttaa yhdestä paikasta.

Sivuston logo on vastaavasti staattisessa sijainnissa `themes/porixi/static/images/`.


Kääntäminen
-----------

Sivusto käännetään komennolla
```
hugo
```

Käännöksen tulos muodostuu staattisina tiedostoina hakemistoon `public/`,
josta ne voi kopioida palvelimelle. Sivusto on tehty alkujaan Hugon versiolla
0.80.0.
