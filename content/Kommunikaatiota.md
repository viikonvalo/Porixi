+++
Date = "2021-02-06T17:17:09.538Z"
Title = "Kommunikaatiota"
Description = "Kommunikaatiota"
Luokat = ["Kurssit","Linux_alkeiskurssi"]
+++

Kommunikaatiota
---------------

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

Tietokone varsinkin kiinteällä Internetyhteydellä on erinomainen
kommunikaatiolaite.

### Irkkaus eli Internet Relay Chat

IRC eli kotoisemmin irkkaus on pikaviestintää ja keskustelukanavia.
Käyttäjä liittyy kanavalle, joita on varsin paljon ja uusia voi perustaa
itsekin. Kirjoitettu teksti lähetetään heti Enter:n painalluksen jälkeen
IRC-palvelimen kautta kaikille kanavalle liittyneille.

Kanava perustetaan kun ensimmäinen käyttäjä liittyy kanavalle ja
poistetaan kun viimeinen käyttäjä poistuu kanavalta. Kun halutaan
perustaa uusi kanava katsotaan kanavan nimi joka ei ole vielä käytössä
ja liitytään tälle kanavalle. Kanavan perustanut käyttäjä saa kanavalle
operaattorioikeudet. Operaattorioikeuksien kanssa on syytä olla
tarkkana, ei pidä antaa oikeuksia epäluotettaville käyttäjille, koska
operaattori voi poistaa operaattorioikeudet kaikilta muilta käyttäjiltä
ja näin kaapata kanavan.

IRC-verkkoja on useita, ja joka verkossa on useita palvelimia ja
mahdollisesti tuhansia kanavia. Haluttaessa jollekin tietylle kanavalle
on tiedettävä mistä IRC-verkosta on kysymys ja joku sen verkon palvelin.
Kannattaa valita lähellä oleva palvelin, esimerkiksi oman
Internetpalveluntarjoajan tai kotimaassa sijaitseva. [Luettelo
IRC-verkoista](http://irchelp.org/irchelp/networks/servers/index.html)
auttaa löytämään oikean verkon ja luettelon sen palvelimista. Suomessa
käytetään paljon IRCNettiä, sen palvelimistakin on
[luettelo](http://irchelp.org/irchelp/networks/servers/index.html).
[Quakenet](http://staff.quakenet.org/servers.phtml) on suosittu
verkkopelaajien keskuudessa. Quakenetissä IRC-palvelimeksi kannattaa
pistää fi.quakenet.org joka tarkoittaa jotain Suomessa olevaa Quakenetin
palvelinta.

IRC-verkossa [Freenode](http://freenode.net/) on aloitteleville
Linux-käyttäjille tarkoitettu kanava
[\#linuxblondit](http://ninnnu.homelinux.net/WP/). Kanavan motto on
*mikään kysymys ei ole liian tyhmä, ja on olemassa vain kohteliaita
vastauksia*.

Koska kanava katoaa kun viimeinen käyttäjä poistuu tavataan käyttää niin
sanottuja botteja. Botti on ohjelma joka pysyy kanavalla ja pitää näin
kanavaa käynnissä. Samalla botti voi antaa tunnistetuille käyttäjille
operaattorioikeudet, koska kanavan perustajakin menettää
operaattorioikeutensa poistuessaan kanavalta. Takaisin tullessaan
perustaja tunnistautuu ja botti antaa hänelle taas operaattorioikeudet.
Eri IRC-verkoissa botit toimivat hieman eri tavoilla, ja botteja on
erilaisiakin, eli yleensä jokaisen bottiohjelman kohdalla pitää opetella
miten sitä käytetään.

Irkatessa tavataan valita kutsumanimi jolla tunnistaudutaan
IRC-verkossa. Tämä niin sanottu nick on vapaasti valittavissa, paitsi
ettei samassa IRC-verkossa voi olla samaa nickiä kahdesti.
IRC-asiakasohjelmassa voi määritellä myös koko nimensä, joka näytetään
muille irkkaajille näiden sitä pyytäessä.

Ohjeita <IRC:n> käytöstä tarjoaa esimerkiksi
[IRCHelp.org](http://irchelp.org/). Lisäksi on syytä lukea käyttämänsä
IRC-asiakasohjelman käyttöohje. Käyttäytymissääntöjä eli irkkaamisen
etikettiä ovat esimerkiksi [Some
advice](http://irchelp.org/irchelp/new2irc.html#advice) -luku IRC
Preludessa, [Idlaa oikein
[IRC:ssä](IRC:ssä)](http://mutru.fi/irc/away.html) ja [Away messages
suck. Please turn them
off](http://sackheads.org/~bnaylor/spew/away_msgs.html).

Jotkut haluavat valokuvansa muiden irkkaajien nähtäville. Tässä auttaa
[IRC-Galleria](http://irc-galleria.net/), jonne voi lähettää valokuvansa
ja tietoja itsestään. Millään tavalla tämä ei ole pakollista, eikä
valokuvista aina tiedä onko se henkilön itsensä vai onko tilalle
vaihdettu paremmin standardivaatimukset täyttävä naamataulu.

Parhaat irkatessa löytyneet jutut voi lähettää
[IRCQuotes](http://www.ircquotes.net/)-sivulle.

Irkin käyttöä voi aluksi harjoitella tekemällä oman kanavan. Siellä ei
sitten ole muita ja saa harjoitella rauhassa. Mennään oikeille kanaville
häiriköimään vasta kun on vähän opittu. Sopivia kanavia kysellä neuvoja
Linuxin käytöstä suomeksi on Freenoden kanavat \#Linuxblondit ja
\#ubuntu-fi. Linux-jakelulle voi löytyä nimikkokanava jostain
IRC-verkosta.

Peruskomentoja, jotka luultavasti toimivat kaikissa
IRC-asiakasohjelmissa ovat:

#### Peruskomentoja irkatessa

- **/NICK \[kutsumanimi\]**  
    Vaihtaa kutsumanimen
- **/QUIT \[Syy\]**  
    Poistuu irkistä ja näyttää muille käyttäjille syyn.
- **/HELP \[komento\]**  
    Näytä ohjeita komennon käytöstä.
- **/WHOIS \[kutsumanimi\]**  
    Näyttää tietoja henkilöstä.
- **/WHOWAS \[kutsumanimi\]**  
    Näyttää tietoja kutsumanimeä viimeksi käyttäneestä.
- **/AWAY \[Viesti\]**  
    Viesti näytetään lähettäjälle kun henkilökohtainen viesti saapuu tai
    kysytään WHOIS. Tällä tavalla voi ilmaista ettei nyt juuri ole irkin
    ääressä.
- **/MSG {kutsumanimi | kanava} \[viesti\]**  
    Lähettää viestin vain nimetylle henkilölle tai kanavalle.
- **/QUERY \[kutsumanimi | kanava\]**  
    Avaa keskustelun nimetyn henkilön kanssa. Keskusteluun avataan yleensä
    oma ikkuna.
- **/NOTIFY \[-\] \[kutsumanimi\]**  
    On mahdollista saada ilmoitus kun nimetty henkilö tulee irkkiin tai
    poistuu irkistä. Tällä komennolla lisätään (tai poistetaan) kutsumanimiä
    ilmoitettavien listalle.
- **/IGNORE \[\[kutsumanimi | tunnus@konenimi\] | viestityyppi\]**  
    Ei enää näytä nimetyn käyttäjän lähettämiä viestejä. Harmittavasti ei
    voi nähdä onko itse jonkun toisen ignore-listalla. Komentamalla /IGNORE
    Taleman ALL ei enää näe mitään käyttäjän Taleman lähettämiä viestejä.
    Viestit saa taas näkymään /IGNORE Taleman NONE.
- **/JOIN \[kanava\]**  
    Liitytään kanavalle.
- **/LEAVE \[kanava\]**  
    Poistutaan kanavalta.
- **/TOPIC \[Kanava | Kanavan otsikko\]**  
    Kanavalle voi asettaa otsikon. Näin voi kuvata mitä aihetta kanavalla on
    tarkoitus käsitellä tai tiedottaa kanavalle tulijoille.
- **/WHO \#kanava**  
    Näyttää kanavalla olijat ja tilatietoa: kutsumanimen jälkeen G
    tarkoittaa poissa (Gone) ja H tarkoittaa paikalla (Here).
- **/ME \[Kerro mitä teet\]**  
    Hauskainen komento, voi kertoa muille mitä on tekemässä. Viesti näkyy
    eri tavalla kuin tavalliset viestit.
- **/CONNECT \[irc-palvelin\]**  
    Toimii irssissä. Aukaisee uuden palvelinikkunan jossa voi liittyä sen
    IRC-verkon palvelimille. Jos irssissä käyttää komentoa /SERVER,
    suljetaan yhteys siihen palvelimeen johon nyt on yhteydessä. Käyttämällä
    /CONNECT voi ottaa yhteyksiä moneen eri palvelimeen elikkä moneen eri
    IRC-verkkoon.

#### Irssi

Irssissä kanavat ovat omissa ikkunoissaan. Niiden välillä hypitään
painamalla **Esc+2**, **Esc+3** ja niin edelleen. Tilaikkuna on numero
1, muut ovat kanavien ikkunoita. Ikkunaan numero 10 pääsee näppäilemällä
**Esc+0**, ikkunaan 11 näppäilyllä **Esc+q** ja vastaavasti näppäimistön
ylimmän kirjainrivin näppäimillä ikkunaan 20 asti, joka on näppäily
**Esc+p**. Jos ikkunoita on tätä enemmän, voi joko mennä tarpeettomaan
ikkunaan ja sulkea sen, **/window close**, tai käyttää komentoa
**/window <ikkunan numero>** ikkunoiden välillä liikkumiseen.
Tilaikkunassa vaihdetaan irc-palvelimien eli irc-verkkojen välillä
**Ctrl+X**, ja irc-palvelimia voi lisätä komennolla **/CONNECT**
palvelin.

![Irssi kanavalla \#linuxblondit](/images/Irssi.png "Irssi kanavalla #linuxblondit")

Lisää tietoa Irssistä kertoo [<http://irssi.org/>](http://irssi.org/).

#### XChat

X-Chat tarjoaa graafisen käyttöliittymän irkkaamiseen. Siinäkin toimivat
nuo kauttaviivalla alkavat komennot, mutta toiminnot löytyvät myös
valikoista.

![XChatin palvelinluettelo](/images/Xchat-palvelinluettelo.png "XChatin palvelinluettelo")

X-Chat lienee helpompi käyttää jos ei ennestään osaa IRC-komentoja.
Avoinna olevat kanavat on helpompi hahmottaa.

![XChat kanavalla \#linuxblondit](/images/Xchat-kanavalla.png "XChat kanavalla #linuxblondit")

Lisää tietoa X-Chatista kertoo [<http://xchat.org/>](http://xchat.org/).

### Sähköposti

Sähköpostia voi lukea ja lähettää hieman eri tavoilla, riippuen
käytetystä yhteyskäytännöstä ja asiakasohjelmasta. Ilmaiset
sähköpostijärjestelmät ovat yleensä Webmaileja. Ostamalla
Internet-yhteyden operaattorilta, saa myös yhden tai useampia
sähköpostilaatikoita. Niihin tulevan postin voi lukea Webmaililla tai
varsinaisilla sähköpostiohjelmilla.

#### Webmail

Webmail toimii vain selaimella, tavallisia sähköpostiohjelmia ei voi
käyttää (paitsi jos webmail on ylimääräisenä lisukkeena tavallisessa
sähköpostipalvelimessa). Tämmöinen sähköpostin käyttö on aivan
samanlaista käyttöjärjestelmästä riippumatta.

![Ilmainen webmail-sähköposti
porilainen.com](/images/Webmail-porilainen.png "Ilmainen webmail-sähköposti porilainen.com")

Ilmaisia webmail-sähköposteja on gmail.com, porilainen.com (Posiona.com
tarjoaa myös kaikki muut Suomen kunnannimet), suomi24.fi, mtv3.fi. Nämä
ovat käteviä matkoilla, postit pääsee lukemaan kunhan löytää selaimen ja
muistaa oman sähköpostinsa asetukset.

Kuvasta
[Media:Webmail-porilainen.png](/images/Webmail-porilainen.png "wikilink")
huomaa roskapostin suuren määrän. Kannattaa käyttää sähköpostissa
roskapostin suodatusta, mieluiten hyvää sellaista, eikä pitää
sähköpostiosoitettaan missään semmoisessa paikassa josta sen saa
ohjelmallisesti luettua (koska roskapostittajat keräävät
järjestelmällisesti osoitteita webbisivuilta, foorumeilta, uutisryhmistä
jne).

#### Thunderbird ja Icedove

Thunderbird (Debian/GNU Linux Etchissä Icedove) sähköposti on aika
helppo saattaa toimintakuntoon. Thunderbirdin saa suomenkieliseksikin.

Yleensä sähköpostipalvelimet osaavat ainakin yhteyskäytännön POP. IMAP
on parempi, eli sitä kannattaa käyttää jos postipalvelin sen osaa. Nämä
tiedot löytyvät Internetpalveluntarjoajan lähettämistä ohjeista, jos ei
löydy ne pitää kysyä.

Saapuvan postin palvelin voi olla samakin kuin lähtevän postin palvelin.
Usein postiaan voi lukea missä vain, mutta Internetpalveluntarjoajat
sallivat postin lähettämisen vain omille asiakkailleen. Lähtevän postin
palvelimen joutuu muuttamaan sopivaksi siirryttäessä toisen
palveluntarjoajan yhteyksille.

#### Fetchmail

Näppärä tapa lukea sähköpostit on noutaa ne omalle koneelle
**fetchmail**-komennolla ja lukea haluamallaan sähköpostiohjelmalla.
Yleensä kaikki sähköpostiasiakasohjelmat osaavat lukea paikallisia
sähköpostilaatikoita. Asetukset tehdään komennolla **fetchmailconf**,
joka osaa joitain asetuksia päätellä itse, itse kirjoitettavat asetukset
ovat vastaavia kuin muillakin sähköpostiohjelmilla.

Debianin kehittäjien keskuudessa **mutt** on sangen suosittu, niinpä
siinä toimiikin kaikenlaiset lisäosat näppärästi ja ohjeistus on
kattava. Mutt tosin on tekstipohjainen eli toimii komentoikkunassa,
mutta toisaalta sitä voi tämän vuoksi helposti käyttää kirjautumalla
sisään toiseen koneeseen ja käynnistämällä **mutt** siellä.

Jos haluaa kokeilla kaikkia sähköpostiasiakasohjelmia, kannattaa välttää
kahden ohjelman käynnistämistä samaan aikaan, tällöin tulee helposti
sotkua sähköpostilaatikon sisällöstä. Tai ainakin käyttäjä sotkeentuu.
Mahdollisesti on myös syytä kokeilun ajan asettaa ohjelma säilyttämään
postit palvelimella, jotta kokeillessa ei hukkaa tärkeitä
sähköpostejaan.
