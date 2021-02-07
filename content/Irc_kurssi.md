+++
Date = "2021-02-06T17:17:07.141Z"
Title = "Irkkausohje"
Description = "Irc kurssi"
Luokat = ["Kurssit","Irkkausohje"]
menu = ["opiskelu"]
weight = 500
+++

Irkkausohje
-----------

{{< menuinclude file="/static/malline/Irc-kurssimenu.md" >}}

Mitä jokaisen irkkaajan on syytä tietää.

### Tavallisimmat komennot

Irkkauksessa pääsee alkuun kun ottaa yhteyden IRC-palvelimeen ja liittyy
kanavalle. Esimerkiksi yhteys OFTC:n palvelimeen muodostetaan komennolla

```
/connect irc.oftc.net
```

Jos komentoa **/connect** ei tunnu olevan, komennetaan
**/server irc.oftc.net**.

Kun ollaan IRC-verkossa OFTC liitytään Porixin kanavalle komennolla

```
/join \#porixi
```

Kanavan nimissä siis on aina ensimmäisenä merkkinä risuaita \#.

Jatkamalla samalla tavalla voi voi muodostaa yhteyden muihin
IRC-verkkoihin ja niiden kanaviin. IRC-asiakasohjelmat osaavat olla
yhteydessä moneen IRC-verkkoon ja moneen kanavaan samaan aikaan. Ei
kannata komennolla **/server** liittyä uuteen IRC-verkkoon, koska se
katkaisee yhteyden muihin verkkoihin. Käytä komentoa **/connect**, se
lisää IRC-verkon entisten jatkoksi. [Luettelo
IRC-verkoista](http://irchelp.org/irchelp/networks/servers/index.html)
auttaa löytämään oikean verkon ja luettelon sen palvelimista.

| IRC-verkko | osoite                    | Webbisivu                   |
|------------|---------------------------|-----------------------------|
| Freenode   | chat.eu.freenode.net      | <http://freenode.net/>      |
| IRCnet     | *irc.omaisp.fi*           | <http://ircnet.org/>        |
| OFTC       | <irc://irc.oftc.net:6667> | <http://www.oftc.net/oftc/> |
| Quakenet   | fi.quakenet.org           | <http://www.quakenet.org/>  |

Graafisessa IRC-ohjelmassa voi IRC-verkon ja kanavan löytää
valikoistakin. Mutta näiden komentojen pitäisi toimia kaikissa
IRC-ohjelmissa, myös graafisissa.

Jos et ole jo vaihtanut kutsumanimeä, nimenäsi on luultavasti
käyttäjätunnuksesi. Samassa IRC-verkossa ei voi olla samaa kutsumanimeä
kahta kertaa, eli mahdollisesti et saa haluamaasi kutsumanimeä jos se on
jo käytössä samaan aikaan. Kutsumanimi eli nickname muutetaan komennolla

```
/nick JokinNimi
```

Kanavalta poistutaan sulkemalla kanavan ikkuna. Myös lopettamalla
irc-ohjelma poistutaan kaikilta kanavilta. Jos et muuten saa
irc-ohjelmaa lopetettua, voit komennolla **/quit** sulkea irc-ohjelmasi
ja halutessasi ilmoittaa poistumisen syyn, tähän tapaan:

```
/quit Näkemiin huomiseen.
```

Jos poistut hetkeksi irkin äärestä ja haluat kavereiden tarvittaessa
tietävän poissaolostasi, voit komennolla **/away** kertoa olevasi poissa
ja syyn.

```
/away Olen ruokatunnilla, takaisin kello 13.
```

Palattuasi komento **/away** *ilman* viestiosaa merkkaa sinut
läsnäolevaksi. Palattuasi komennat siis pelkän

```
/away
```

Komennolla **/who \#kanavannimi** saa tulosteen josta näkee keitä
kanavalla on, ja ketkä ovat paikalla (H eli Here) ja ketkä ovat
merkinneet itsensä poissaoleviksi (G eli Gone). Tulostus tulee irssin
ikkunaan numero 1. Komento **/wii lempinimi** näyttää tiedot yhdestä
käyttäjästä.

[IRC:ssä](IRC:ssä) on mahdollista keskustella myös kahden kesken.
Komento **/msg** lähettää viestin vain annetulle kutsumanimelle ja avaa
uuden ikkunan jossa keskustellaan kahden kesken. Komento on siis

/msg JokinNimi

Komento **/query** on kuten **/msg**, mutta siirtää sinut samalla
keskusteluikkunaan.

### Irssi

Irssin ohjeita löytyy ohjelman [omalta webbisivulta](http://irssi.org).
Tässä ohje miten irssiä käytetään kun pitää olla monella kanavalla jotka
mahdollisesti ovat eri IRC-verkoissa.

Tällöin ikkuna ykkönen on erikoisasemassa, siinä voi näppäilyllä
![kuva:Computer_key_Ctrl.png](/images/Computer_key_Ctrl.png "fig:size=30px")-![kuva:Computer_key_X_T.png](/images/Computer_key_X_T.png "fig:size=30px")
vaihtaa IRC-verkosta toiseen eli IRC-palvelinten välillä. Kun on oikea
IRC-verkko valittuna, komennolla **/join \#kanavannimi** voi liittyä
siinä verkossa olevalle kanavalle.

Kanavien eli irssin ikkunoiden välillä vaihdetaan joko komennolla
**/window *numero*** tai pikanäppäilyllä painamalla ensin näppäintä Esc,
päästämällä Esc ylös ja sitten numeronäppäintä. Näin saadaan ikkunat 1 -
10. Ikkunat 11 - 20 saadaan kirjaimilla qwertyuiop eli näppäimistön
kirjainosan ylärivin näppäimillä. Jos ikkunoita on yli 20 voi joko
käyttää komentoa tai sulkea turhia ikkunoita menemällä suljettavaan
irssin ikkunaan ja komentamalla **/window close**.

Esimerkiksi ikkunaan yksi päästään pikanäppäilyllä
![kuva:Computer_key_Esc_T.png](/images/Computer_key_Esc_T.png "fig:size=30px")
![kuva:Computer_key_num_row_1_T.png](/images/Computer_key_num_row_1_T.png "fig:size=30px"),
ikkunaan numero 15 näppäilyllä
![kuva:Computer_key_Esc_T.png](/images/Computer_key_Esc_T.png "fig:size=30px")
![kuva:Computer_key_T_T.png](/images/Computer_key_T_T.png "fig:size=30px").

Irssi näyttää alareunan tilarivillään missä ikkunoissa on lukemattomia
viestejä. Korostusvärillä näytetään ne ikkunoiden numerot joissa on
nimellä lähetettyjä viestejä.

### Lisää irkkausohjetta

Irkissäkin on hyvä käytös kultaa ja räyhärit saavat porttikieltoa.
Jotkin seikat ärsyttävät niin paljon että ihan webbisivu tehdään, kuten
[Idlaa oikein IRC:ssä](http://mutru.fi/irc/away.html). Lisää
vastaavaa on [Absoluuttinen Totuus Irkistä](http://mutru.fi/irc/).

Pidempi irkkausohje on [Kommunikaatiota](Kommunikaatiota "wikilink").
Lisäksi muuallakin on juttua, esimerkiksi
[<http://winku.fi/oppaat/irc/>](http://winku.fi/oppaat/irc/).

--[tale](/käyttäjä/Taleman "wikilink") 6. helmikuuta 2008 kello 10.20
(EET)
