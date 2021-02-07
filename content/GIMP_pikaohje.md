+++
Date = "2021-02-06T17:17:05.078Z"
Title = "GIMP pikaohje"
Description = "GIMP pikaohje"
Luokat = ["Kurssit","Gimp"]
menu = ["opiskelu"]
weight = 700
+++

Valokuva julkaisukuntoon GIMP:llä
---------------------------------

GIMP on [GNU Image Manipulation Program](http://gimp.org/). Vastaavia
sovelluksia on Photoshop.

Tässä tietoisku miten GIMP:llä saadaan valokuva julkaisukelpoiseen
kuntoon. Suureellisemmat kuvankäsittelyt pitää opetella muualla.

GIMP:n eiku-toiminto on **Control-Z**.

Toiminnot olisi tehtävä tässä järjestyksessä, muuten kuvasta katoaa
informaatiota, tehdään turhaa työtä tai muuten vaan menee jotain
pieleen.

### Kuvan suoristus ja rajaus

Gimpin kuvaikkuna kokoruutuun. Voi siirtää kuvaikkunan toiseen
työpöytään tai toiselle näytölle niin jää oma työpöytä tai näyttö GIMP:n
työkaluikkunoille.

Laajenna kuva mahdollisimman isoksi siten että se näkyy kokonaan:
**Vaihto-Control-J**. (Tämä näköjään riippuu GIMP:n versiosta. Versiossa
2.8 toiminnon pikanäppäily on tuo edellä mainittu, aikaisemmin se oli
**Vaihto-Control-E**.)

Suorista horisontti kiertämällä kuvaa: **Vaihto-R**. Minusta helpompi
suoristaa kun Kierron asetuksista valitsee Käänteinen (korjaava).

Rajaa kuva "rajaa ja muokkaa kokoa" -työkalulla: **Vaihto-C**.
Kuvasuhteen voi pakottaa Suorakulmiovalintatyökalun asetuksissa.
Esimerkiksi [kymppikuvan](http://fi.wikipedia.org/wiki/Kinofilmi) mitat
ovat 10 cm \* 15 cm, eli kuvasuhde on 2:3. Kun raja on saatu haluttuun
kohtaan, painetaan Enter.

### Valotuksen korjaus

Valikon toiminto Värit | Säätöarvot. Ennen GIMP:n versiota 2.4 toiminto
oli Taso | Värit | Väritasot.

Säädä musta kolmio histogrammin alkuun ja valkoinen kolmio loppuun.
Keskimmäisellä kolmiolla voi säätää keskisävyjä.

### Punasilmäisyyden poisto

Punasilmäisyydellä tarkoitetaan valokuvassa näkyviä kirkkaanpunaisia
silmiä. Ilmiö johtuu silmän verkkokalvolta suoraan takaisin kameraan
heijastuvasta salaman valosta. Kuvaa otettaessa punaisilta silmiltä
välttyy käytettäessä ulkoista salamaa joka on riittävän kaukana kameran
linssistä. Kameran sisäänrakennetulla salamalla tulee punasilmiä
helposti jos kohde katsoo suoraan kameraan. Jos kuvaa otettaessa saa
kuvattavat henkilöt komennettua kohdistamaan katseensa kuvaajan
olkapäähän tai muuhun tarpeeksi kaukana kamerasta olevaan kohteeseen
pitäisi myöskin välttyä punasilmiltä.

Vanhemmissa GIMP-versioissa helpoin tapa poistaa punaiset silmät on
maalata musta ympyrä silmäterään. Tämä on nopea tapa ja toimii jos
silmäterä on kuvassa niin pieni ettei siinä näy yksityiskohtia.

Gimp versiossa 2.4 luvataan olevan toiminto punasilmäisyyden poistoon.
Toiminto on näppärä ja helppo. Punasilmäisyyden poisto tapahtuu
muuttamalla kuvasta punainen väri mustaksi. Tällöin silmäterän
yksityiskohdat säilyvät. Koska kuvassa lienee punaista muuallakin kuin
punasilmissä, on syytä ensin rajata käsiteltävä alue vain silmiin, tai
ääritapauksessa silmäterään. Kuvaa voi ensin suurentaa (Näytä |
Suurenna). Valitaan suorakulmainen tai ellipsin muotoinen alue,
työkaluvalikosta tai pikanäppäimillä R tai E. Ellipsivalinta jolla saa
valittua myös ympyrän muotoisen alueen on parempi valittaessa vain
silmäterä (koska se on pyöreä kun kohde on katsonut suoraan kameraan).
Sitten valikosta Suotimet | Paranna | Punasilmäisyyden poisto valitaan
toiminto, kynnysarvoa voi kokeilla säätää ja tarkistaa esikatselusta
mitä se vaikuttaa.

Lisää ohjeita ja muita tapoja neuvotaan netissä, googleta "red eye
reduction". Esimerkiksi [How to Quickly Remove Red Eye With
Gimp](http://www.wikihow.com/Quickly-Remove-Red-Eye-With-Gimp).

### Roskien tai vikojen poisto kuvasta

Kloonaustyökalu eli leimasin, pikanäppäin **C**. Saa käyttöön
"ruudullista maalia". **Control**-klikkaus mallikohdassa. Hiiren nappula
pohjassa maalataan. Linjaus vaikuttaa maalaamisen toimintaan, vissiin
Linjassa on se käyttökelpoisin. Voi maalata myös toisesta tasosta tai
kuvasta otetun mallin mukaan. Katso ettei Kloonaus-työkalun ikkunassa
ole Linjaus Rekisteröity, en ole tajunnut miten se toimisi.

### Kuvan koon muuttaminen

Valikosta Kuva | Skaalaa kuvaa ...

Merkitään kuvan mitat, leveys ja korkeus, Sitten merkitään
tulostustarkkuus. Lopuksi oikeasta alanurkasta Skaalaa-painike. Jos
paperivedoksen sijaan kuva julkaistaan netissä, kannattaa kuvan leveys
ja korkeus merkitä kuvapisteinä. 800\*600 voisi olla sopiva koko,
silloin kuva näkyy kokonaan pienilläkin näytöillä vaikka selaimen palkit
ja ikkunan kehys veisi tilaa. HD tarkkuuden näyttö on 1920\*1080
kuvapistettä, harvalla on sitä isompia näyttöjä eli HD-tarkkuutta
isompia kuvia ei hyödytä tehdä tietokoneella katsottaviksi.

### Tallennus

Tässä vaiheessa kannattaa tallentaa käsitelty kuva. Katso ettet tallenna
alkuperäisen kuvan päälle, eli muutat nimeä tai tallennat toiseen
hakemistoon. Kuva kannattaa tallentaa GIMP:n omassa tiedostomuodossa
(xcf), koska tällöin tallentuu kaikki kuvan informaatio, ja kuvan
käsittelyä voi jatkaa myöhemmin. Jos tallentaa vain TIFF-tiedostona, ei
tallenneta esimerkiksi tasoja, ja JPG-tiedoston pakkauksessa katoaa
informaatiota.

### Terävöinti

Terävöinti hukkaa kuvasta informaatiota, muistithan *tallentaa* kuvan
ennen kun terävöit?

Valikko Suotimet | Paranna | Unsharp mask

Terävöinti tehdään julkaisumuodon mukaan. Paperille vedostettavaa voi
terävöittää aika paljon, sopiva määrä voi ruudulla näyttää liikaa
terävöidyltä.

|             |                                                |
|-------------|------------------------------------------------|
| Säde:       | 0,5 - 1,5                                      |
| Määrä:      | 0,5 - 2,0                                      |
| Kynnysarvo: | 0 (jos kovin rakeinen, koita arvon nostamista) |

### Kuvan julkaisu

Paperille tulostettaessa helpointa on tulostaa suoraan GIMP:stä. Jos
tulostin on jossain muussa koneessa, pitää kuljettaa tiedostona,
tallenna tarpeeksi hyvälaatuisena semmoiseen tiedostomuotoon, jota siinä
tulostinkoneessa oleva ohjelma pystyy tulostamaan. Toiminto Tiedosto |
Vie muodossa antaa valita mihin tiedostomuotoon tallennetaan.

Kuvatiedostoksi tallennettaessa JPG eli JPEG lienee käyttökelpoisin, se
on nimenomaan valokuville tarkoitettu tiedostomuoto. JPG on pakattu
tiedostomuoto, liian suurella pakkauksella kuvan laatu huononee silmin
nähden. Tapaan pistää pakkauksen arvoon 20, ja siitä esikatselun kera
kasvattaa pykälä kerrallaan kunnes kuvassa ei enää huomaa muutosta. Näin
on kuvatiedoston koko saatu mahdollisimman pieneksi huonontamatta kuvan
laatua silmiinpistävällä tavalla.

Lisää lukemista
---------------

GIMP-ohjeita on ulkomaankielillä vaikka kuinka, mutta suomeksi
vähänlaisesti. Mutta Wikibooksissa on suomeksi hyvä
[GIMP-kirja](http://fi.wikibooks.org/wiki/GIMP).

--Taleman 21. joulukuuta 2008 kello 10.39 (EET)
