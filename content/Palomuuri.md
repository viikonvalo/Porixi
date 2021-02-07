+++
Date = "2021-02-06T17:17:19.981Z"
Title = "Palomuuri"
Description = "Palomuuri"
Luokat = ["Linux alkeiskurssi"]
+++

Palomuuri
---------

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

Palomuuri (firewall) tarkoittaa ohjelmistoa tai laitetta joka estää
luvattoman tietoliikenteen ulkopuolelta tietokoneelle. Jos tietokoneessa
on nettiyhteys, palomuuri on nykyään välttämätön.

Linux-ytimessä on palomuurin tarvitsema toiminnallisuus valmiina.
Tarvitaan vain käyttöliittymä jolla palomuurin asetukset tehdään ja
palomuuri käynnistetään ja sammutetaan. Toki *voi* tehdä ytimen jossa
tarvittavia osia ei ole mukana, mutta luultavasti kaikkien
Linux-jakeluiden ytimessä ne on käännetty mukaan.

Debian GNU/Linux tarjoaa useitakin vaihtoehtoisia palomuurin
hallintaohjelmia. Periaatteessa palomuurin käyttöönotto on varsin
yksinkertaista: sallitaan kaikki yhteydet jotka avataan sisältä
ulospäin, ja kielletään kaikki yhteydet ulkoa sisäänpäin lukuunottamatta
niitä jotka on jo avattu sisältä päin. Tällaisen palomuurin tekee
ohjelmalla [firestarter](http://www.fs-security.com/) hyvin helposti.

### Firestarter

Firestarterin saa nopeasti käyttöön ja se tekee peruspalomuurin hyvin
vähäisellä säätelyllä.

*screenshotit asetusruuduista olis kiva saada*

Kun firestarterin asetukset on tehty, se käynnistyy automaattisesti.
Jatkossa firestarter käynnistyy joka kerta Linux-järjestelmän
käynnistyessä. Jos on soittoyhteys eli modeemi, Firestarter pitää valita
käynnistyväksi soittoyhteyden ajaksi.

Ei ole välttämätöntä pitää Firestarterin ikkunaa auki ruudulla,
palomuuri toimii taustalla vaikka käyttöliittymäohjelman sulkee. Toki
voi seurata palomuurin estämiä yhteyden avauksia Hits-välilehdeltä.
Lisää tietoa Firestarterista löytyy ohjelman
[webbisivulta](http://www.fs-security.com/) ja ohjelman mukana
asentuneista käyttöohjeista.

### Arno-iptables-firewall

Monipuolisempi palomuuri saadaan esimerkiksi
[arno-iptables-firewall](http://rocky.eld.leidenuniv.nl/)
komentotiedostolla. Tämä on siitäkin näppärä, että toimii vaikkei
palomuurikoneessa olisi asennettuna graafista käyttöympäristöä.

Mikäli palomuuriin pitää avata portteja palveluita varten tai muuta
erikoisempaa säätelyä, on arno-iptables-firewall käytännöllisempi kuin
Firestarter.
