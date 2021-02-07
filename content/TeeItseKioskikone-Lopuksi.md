+++
Date = "2021-02-06T17:17:34.473Z"
Title = "TeeItseKioskikone-Lopuksi"
Description = "TeeItseKioskikone-Lopuksi"
Luokat = []
+++

Lopuksi
=======

{{< menuinclude file="/static/malline/TeeItseKioskikone-menu.md" >}}

Jos kioski tulee yleiseen käyttöön kannattaisi hiiri olla optinen tai
liimata mekaanisesta hiirestä kuulan luukku kiinni. Muuten hiiren kuula
pakkaa katoamaan käyttäjien mukaan.

Jos kioskikäyttö on jatkuvaa, tuntuisi kiintolevylle asennettu
kioskijärjestelmä paremmalta. Sitä voi helpommin muokata mieleisekseen
ja asennusta voi päivittää. Satunnaisessa käytössä Live-CD kelpaa.
USB-muistilta käynnistämisessä on ongelmana ettei vanhat koneet osaa
käynnistyä USB-laitteelta, ja vanhoja koneita kioskikäyttöön olisi
saatavilla ilmaiseksi.

Jos kioskikoneet ovat valvomattomassa paikassa, ei saisi olla irtoavia
osia. Kiintolevy olisi tässäkin valmiiksi sopiva. CD-asema pitäisi
siirtää kototelon sisäpuolelle, samoin kuin USB-portti jossa boottaava
USB-muisti.

Jos kioskikone on paikassa jossa ei sentään pääse osia keräämään
mukaansa, on silti hankalaa kun käyttäjä touhuttuaan koneen sekaisin
poistuu paikalta. Seuraava käyttäjä ei luultavasti osaa palata
alkutilaan. Esimerkiksi selaimen voi sammuttaa, mennä konsoliin
painamalla Control-Alt-F1 tai vastaavaa.

USB-tikulta käynnistämistä ei tällä kertaa ennätetty kokeilemaan, sitä
voisi vielä selvitellä. Etuna Live-CD:hen verrattuna olisi helpompi
muokattavuus, eli USB-muistin voi liittää tavanomaiseen tapaan ja
muokata tiedostoja. CD pitää buildata ja polttaa uusi kopio,
vaivalloisempaa ja kestää kauemmin testailla. Esimerkiksi DSL:n
valikoissa on toiminto boottaavan USB-muistin kirjoittamiseen, se olisi
aika nopea tapa eikä DSL tarvitse kovin isoa muistitikkua.

R-Kiosk
-------

R-Kiosk on aika hyvä, mutta jos halutaan pääsy vain annettuun
sivujoukkoon joudutaan etukäteen valmistelemaan aika paljon. R-Kioskin
oletus ilman navigointipalkkia estää kyllä siirtymisen mielivaltaiselle
sivulle, mutta sivujoukon sisällä siirtyminen on hoidettava sivuilla
olevilla linkeillä. Alkusivulla pitäisi olla linkit sivujoukon sivuille,
ja joka sivulla linkki josta pääsee ainakin takaisin alkusivulle tai
mahdollisesti vastaavasti kuin tässä kirjoitelmassa eli
sisällysluettelolaatikko jossa on linkki kaikkiin kirjoitelman sivuihin.
Nähtävästi R-Kioskin tekijä on olettanut sallitun sivujoukon olevan
etukäteen tällä tavalla valmisteltu.

Jos selaimen navigointipalkin pistää näkyviin, katoaa selausrajoitus.
Tällöin ehkä palomuurissa voisi sulkea pois turhat sivut, mutta tämäkin
vaatisi järjestelyä etukäteen.

R-Kiosk muokkaa kioskikäyttöön vain selaimen, lisäksi olisi
käyttöjärjestelmän puolella saatava kioskikäyttäjän istunto
käynnistymään koneen bootatessa.

Käyttöjärjestelmä
-----------------

Käyttöjärjestelmän puolella kioskikäyttö tarkoittaa halutun
kioskikäyttäjän automaattista sisäänkirjautumista (siis ilman salasanan
kysymistä) bootissa ja haluttujen ohjelmien käynnistymistä istuntoon.
Olemme olettaneet, että haluttu ohjelma on pelkästään selain.

Lisäksi olisi estettävä käyttäjän poistuminen kioskiympäristöstä. Jos
selaimen sammuttamista ei voi estää, järjestää niin ettei käynnistetä
selainta suoraan, vaan käynnistetään komentotiedosto joka selaimen
sammuessa käynnistää sen heti uudelleen. X-istunnon sammuttaminen
pitäisi myös estää, samoin kuin konsolille pääsy painamalla
Control-Alt-F1.

Koneen sammuttaminen siististi pitäisi mahdollistaa. Jos käytetään
Live-CD:ltä, tästä ei ole niin väliksi mutta kiintolevylle asennettu
käyttöjärjestelmä tulisi ajaa siististi alas ja antaa ohjelmiston
sammuttaa virrat koneesta. Lisäksi selain saattaa käynnistyessään
valittaa jos edellinen selainistunto on killattu. Kioskikoneet voisi
vaikka etäsammuttaa jos niissä on SSH-palvelin asennettuna, sitten voi
verkon jostain koneesta pääkäyttäjän salasanan tietämällä sammuttaa.
Koneet voisi myös ajastetulla tehtävällä pistää sammumaan illalla. Jos
koneet pitää aamulla saada automaattisesti käynnistettyä, voi BIOS ehkä
osata ajastetun käynnistyksen. Tämmöinen voi olla tarpeen jos kioskikone
on lukitussa kaapissa ja virtakytkimeen ei pääse käsiksi. Jos paikalla
ei ole asiantuntevaa etäsammuttajaa, pitäisi olla joku konsti jolla
koneen ääressä istuva saisi koneen sammutettua. Toisaalta voi olla ettei
sammuttamista kannata tehdä liian helpoksi, sitten satunnaiset
käyttäjätkin sammuttelevat konetta poistuessaan huvikseen, tavan vuoksi
tai koska eivät luota kaikkien istunnon tietojen poistuvan selaimen
uudelleenkäynnistyksellä.

Laitteesta
----------

Ubuntulla tehty kioskikone toimi hyvin ja on aika helppo tehdä, **gdm**
hoitaa automaattisen sisäänkirjautumisen ja R-Kiosk tekee
kioskiselaimen. Hankaluutena on melkoiset konevaatimukset, pitää olla
sen verran tehokas kone että Ubuntu toimii riittävän ripeästi.

Debianin peruskokoonpano johon on lisätty suomenkielinen Iceweasel ja
sen vaatimat paketit ei vie paljon levytilaa eikä muistiakaan kulu
vallan mahdottomasti. Tämmöisen pystyy asentamaan huomattavasti
pienempään tietokoneeseen. Laitevaatimukset on varsin pienet joten
sopivia koneita on jo jaossa ilmaiseksi. Muistit voi joutua keräämään
kahdesta ilmaiskoneesta jos ei ole valmiiksi 128 Mtavua. Myös DSL ja
Webconverger toimivat tämmöisessä vanhemmassa koneessa, ne tulevat
lisäksi Live-CD:ltä käynnistettynä toimeen ilman kiintolevyä eli senkään
puute ei haittaa.

Tapio ja Ilkka
