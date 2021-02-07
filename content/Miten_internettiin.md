+++
Date = "2021-02-06T17:17:16.845Z"
Title = "Miten internettiin"
Description = "Miten internettiin"
Aliases = ["/Miten_internettiin?"]
Luokat = ["Linux alkeiskurssi"]
+++

Miten Internettiin?
-------------------

{{< menuinclude file="/static/malline/Akurssimenu.md" >}}

### ADSL tai kaapeli

Linuxin asennin tunnistaa ethernetkortin ja sen kautta nettiyhteys
yleensä toimii helposti. Tämmöisiä nettiyhteyksiä on ADSL- tai
kaapelimodeemien kautta, jos modeemi on ulkoinen. ADSL-modeemi tai
kaapelimodeemi kertoo tarvittavat verkkoasetukset tietokoneelle, eli
tietokone noutaa DHCP:llä sopivat asetukset. Jos modeemi on tietokoneen
sisäinen kortti, pitää sille olla ajurit Linuxiin.

### Soittoyhteys eli modeemi

Puhelinverkossa käytettävän modeemin kanssa Internettiin mentäessä ei
päästä ihan näin vähällä. Helpoin tapa lienee kytkeä modeemi päälle ja
asentaa **wvdial**. Tällöin **wvdial** kysyy puhelinnumeron,
käyttäjätunnuksen ja salasanan sekä etsii modeemin.

Tämän jälkeen root voi käynnistää nettiyhteyden komennolla wvdial.
Mikäli koneessa on ethernetkortti, on syytä ensin sulkea sitä vastaava
liitäntä, eli komento on **ifdown eth0** (Debian GNU/Linuxissa ja
Ubuntussa). Sulkemalla **wvdial** esimerkiksi painamalla **Ctrl+c**
yhteys katkeaa.

Käyttämällä komentoa **sudo** voi root järjestää muillekin käyttäjille
mahdollisuuden käynnistää wvdial.

Kun nettiyhteys on päällä, kaikki koneen käyttäjät voivat sitä käyttää.

Muista ottaa käyttöön myös [palomuuri](/palomuuri "wikilink").

### Langaton eli WLAN

Ensimmäinen pulma on Linux-ajurit WLAN-kortille. Ajuritilanne on ollut
varsin huono, kannattaa laitetta hankittaessa varmistua Linux-ytimessä
olevan vakiona ajurit kyseiselle WLAN-kortille tai valmistajan tarjoavan
vapaan ajurin joka toimii käytettävissä ytimen versioissa.

Ajuritilanne on parantunut merkittävästi. Myös langattoman verkon
käyttöönotto on helpottunut Network Managerin myötä. Tuolle
sovellukselle kerrotaan verkon SSID ja salasana, yhteys syntyy kotvasen
kuluttua.

### 3G

Ubuntussa versiosta 8.10 alkaen on ollut mukana Network Manager joka
osaa muodostaa yhteyden myös 3G-verkon kautta. Joissain läppäreissä on
3G-modeemi sisäänrakennettuna, muissa koneissa voi hankkia
USB-liitäntäisen nettitikun.
