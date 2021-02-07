+++
Date = "2021-02-06T17:17:00.951Z"
Title = "Asennusvertailu-Ubuntu"
Description = "Asennusvertailu-Ubuntu"
Luokat = []
+++

Ubuntu 9.10
===========

{{< menuinclude file="/static/malline/Asennusvertailu-menu.md" >}}

Ilmeni vaikeuksia Linuxin asentamisessa. Koneeseen oli asennettu Ubuntua
ja Debiania useita kertoja, mutta Windows 7:n asentamisen jälkeen
Linux-asennukset kaatuivat joka kerta. Piti vaihtaa uudet muistikammat
koneeseen, sitten vasta alkoi Linux toimimaan.

Tässä pikaiset mittaukset, ensi viikolla tulee tarkemmat kun on useampi
porixoidi paikalla mittaamassa, pitämässä kirjaa ja käyttämässä
asenninta.

Windowsin asennuksessa meni yhdeksän ja puoli minuuttia ennen kuin
ruudulla alkoi näkymään jotain tapahtuvankin. Ubuntussa oli ensimmäiset
3 minuuttia 27 sekuntia ruudulla vain kirkkautta vaihtava kuvake
keskellä, eli ei kovin hyvin näe Ubuntussakaan asentimen tekevän jotain
ja asennuksen etenevän. Mutta Ubuntussa sentään CD-asema tai
kiintolevyasema teki koko ajan jotain, ja voi päätellä jotain olevan
tekeillä.

Perusasennus vei 21:32, päivitys jossa päivitettiin 203 pakettia eli
yhteensä 150,8 Mtavua vei 22:09. Ajurien asennus vei 4:44, eli
asennettiin NVidian näytönohjaimen suljettu ajuri, jota ajurien hallinta
tarjosi asennettavaksi. Yhteenä 48:25. Ajurien asennuksen eli NVidian
suljetun ajurin voisi jättää pois, se tarvitaan vain jos haluaa
3D-kiihdytyksen näytönohjaimeen. 2D-käytössä avoin ajuri toimii aivan
hyvin. Päivitys vei Ubuntussa enemmän aikaa kuin Windows 7:ssa, koska
Ubuntun päivitystiedostojen koko oli suurempi kuin Windowsissa.
Käyttöjärjestelmät oli julkistettu viikon välein, eli tilanne oli
kohtuullisen tasapuolinen.

YLE Areena ja Youtube ei toimi tässä vaiheessa. Mutta kun asennettiin
vielä ubuntu-restricted-extras, toimivat molemmat. Asennusaika 7:10.

Päivitysten ja ajurien asentamisen jälkeen bootattiin yksi ylimääräinen
kerta, ennen kuin mitattiin seuraavat ajat: Käynnistys 36 sekuntia,
sisäänkirjautuminen 12 sekuntia, sammutus 12 sekuntia.

Viralliset mittaukset
---------------------

| Selain | Toimistoohjelmat | Sähköposti | Teksturi | Laskin | Grafiikka | Musasoitin | Elokuvakatselin | CD-poltto | CD ripper | PDF-katselin |
|--------|------------------|------------|----------|--------|-----------|------------|-----------------|-----------|-----------|--------------|
| Firefox | OpenOffice.org | Evolution | Nano, GEdit | On  | Gimp | Rytmilaatikko | Totem | Brasero | ei  | Evince |

Perusasennus 21:23, päivitys ajan tasalle 22:59, ajurien asennus 04:51,
Ubuntu restricted extras 06:41. Päivitys kesti paljon kauemmin kuin
Windowsissa, noudettavan datasetin kokokin oli paljon suurempi, eli 203
tiedostoa yhteiskooltaan 150,8 Mt. Ajurien asennus tarkoittaa
näytönohjaimen suljetun ajurin asentamista, eli NVidian ajuri. Paketti
ubuntu-restricted-extras sisältää suljettuja tiedostomuotoja tukevia
koodekkeja, sen asentamisen jälkeen Flash player toimii selaimessa sekä
iso joukko videotiedostojen tallennusmuotoja

Seuraavat ajat mitattiin kun oli käynnistetty yksi ylimääräinen kerta
yllä olevien päivitysten ja asennusten jälkeen: Käynnistys 33 s,
sisäänkirjautuminen 9 s, sammutus 7 s.
