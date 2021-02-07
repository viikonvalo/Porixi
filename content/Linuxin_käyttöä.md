+++
Date = "2021-02-06T17:17:14.085Z"
Title = "Linuxin käyttöä"
Description = "Linuxin käyttöä"
Luokat = ["Kurssit","Linux_alkeiskurssi"]
+++

### Linuxin käyttöä

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

Kun on kirjauduttu sisään käynnistettäviä sovelluksia voi etsiä
valikoista tai useimmin tarvittavat voi itse lisätä työkalupalkkiin
nopeammin löydettäviksi. Palkkiin voi lisätä myös vetolaatikoita jos
tila muuten loppuisi.

![Vasenkätisen ja oikeakätisen hiiren painikkeiden järjestys](/images/Hiiren_painikkeet.xfig.png "Vasenkätisen ja oikeakätisen hiiren painikkeiden järjestys")

Linuxissa ja muissa Unixeissa graafinen käyttöympäristö on useimmiten X
Window, jossa tavataan käyttää kolmipainikkeista hiirtä
osoitinlaitteena. Hiiren voi määritellä vasenkätiseksi, jolloin
painikkeiden järjestys muuttuu peilikuvakseen. Oikeakätisessä hiiressä
painikkeet ovat 1, 2 ja 3, vasenkätisessä 3, 2 ja 1. Painikkeella 1
käynnistetään ohjelmia ja avataan valikoita, painikkeella 3 usein
avataan asetusvalikko. Painiketta 2 käytetään leikatessa ja liimatessa
liimaamiseen, eli X Window maalaa alueen kun pidetään painiketta 1
pohjassa, alueen saa kopioitua kohdistimen osoittamaan paikkaan
painikkeella 2.

Hiiren keskimmäinen painike voi olla rulla, jolloin rullaa pyörittämällä
voidaan esimerkiksi vierittää ikkunaa. Kaikki sovellukset eivät
välttämättä ymmärrä rullan pyörityksiä. Rulla toimii myös painikkeena,
eli sitä voi käyttää kuten muitakin painikkeita ja lisäksi pyörittää.

![Mennään muuttamaan
hiiriasetuksia](/images/muutetaan_hiiriasetuksia800.png "Mennään muuttamaan hiiriasetuksia")

Hiiren voi halutessaan muuttaa vasenkätiseksi työpöydän asetuksista.
Hiiren muitakin ominaisuuksia voi säätää mieleisekseen.

![Hiiri
vasenkätiseksi](/images/hiiri_vasuriksi.png "Hiiri vasenkätiseksi")

Asetukset ovat käyttäjäkohtaisia, omat muutokset eivät vaikuta
esimerkiksi muiden käyttäjien hiiren kätisyyteen. Asetuksia voi siinä
mielessä muutella aika vapaasti, mutta sen verran voisi varoa ettei
sotke asetuksia niin perusteellisesti ettei enää saa toimivia asetuksia
takaisin.

Jos hiiressä on vain kaksi painiketta, saa keskimmäisen painikkeen
painalluksen painamalla molemmat alas. Asennusohjelma luultavasti teki
asetukset tähän sopiviksi, mutta jos ei tehnyt, komennolla

```
dpkg-reconfigure xserver-xfree86
```

voi säätää hiiren
toimintaa ja valita Emulate3Buttons käyttöön.

Joissain ohjelmissa hiiren painikkeet vaikuttavat erilailla, saattavatpa
vaihdella ohjelman sisälläkin suoritettavan toiminnon mukaan.
Esimerkiksi piirtelyohjelma xfig vaihtaa painikkeisiin sidottuja
toimintoja ja näyttää ikkunan oikeassa yläkulmassa mitä painikkeista
milloinkin tapahtuu.

![XFig näyttää hiiren painikkeiden toiminnot](/images/Xfig-hiiri2.png "XFig näyttää hiiren painikkeiden toiminnot")

Paneeliin eli yläreunan työkalupalkkiin (sen voi siirtää muuhunkin
kohtaa ruutua vetämällä hiirellä tai hiiren kolmospainikkeella tyhjää
kohtaa kliksauttamalla tulevasta valikosta) voi lisätä yleisimpien
käyttämiensä ohjelmien käynnistimet.

![Säätilanäytön lisäys paneeliin](/images/Paneeliin_saatila.png "Säätilanäytön lisäys paneeliin")

Jos innostuu lisäilemään sovelluksia paneeliin niin paljon, että tila
loppuu, voi lisätilaa järjestellä vetolaatikoilla.

![Vetolaatikon lisäys paneeliin (hiiren painikkeella 3)](/images/Paneeliin_vetolaatikko800.png "Vetolaatikon lisäys paneeliin (hiiren painikkeella 3)")

![Vetolaatikossa kolme käynnistintä](/images/Vetolaatikko800.png "Vetolaatikossa kolme käynnistintä")

Linuxiin on saatavilla monta erilaista selainta (browser). Eniten
käytetty lienee Mozilla, sen saa myös Windows-koneille jos ei halua
käyttää Internet Exploreria. Mozilla sisältää selaimen lisäksi
monenlaista muutakin sovellusta, esimerkiksi Firefox tai Galeon ovat
vain selaimia.

![Käynnistetään Mozilla-selain valikosta](/images/Selain800.png "Käynnistetään Mozilla-selain valikosta")

Debian GNU/Linuxissa on tekijänoikeudellisista syistä Firefoxin nimi
pitänyt muuttaa, se on nyt *Iceweasel*. Kyseessä on silti ihan sama
selain kuin Firefox, nimi vain on muuttunut. Samoin on Thunderbirdin
nimi Debianissa *Icedove*.

Hiiren käyttöä voi harjoitella selaimella tai vaikkapa pelaamalla
pasianssia, joka löytyy Sovellukset-&gt;Pelit-valikosta.

#### Ikkunoiden hallintaa

Työpöytäympäristö Gnome mahdollistaa useamman työtilan käytön. Tällöin
on käytössä esimerkiksi neljä kuvaruudullista, joista yhtä kerrallaan
näytetään.

![Työtilan näyttöä voi muokata](/images/Tyotilat.png "Työtilan näyttöä voi muokata")

Ikkunoita voi "liimata ruutuun" eli saada näkymään jokaisessa
työtilassa, tai siirtää toiseen työtilaan.

![Ikkunan vasemman yläkulman toimintovalikon saa esiin hiiren painikkeella 3](/images/Ikkunat_pinoon.png "Ikkunan vasemman yläkulman toimintovalikon saa esiin hiiren painikkeella 3")
