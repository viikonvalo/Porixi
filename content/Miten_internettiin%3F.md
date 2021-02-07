+++
Date = "2021-02-06T17:17:16.495Z"
Title = "Miten internettiin%3F"
Description = "Miten internettiin%3F"
Luokat = ["Linux alkeiskurssi"]
+++

Miten Internettiin?
-------------------

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

Kun nettiyhteys on päällä, kaikki koneen käyttäjät voivat sitä käyttää.

Muista ottaa käyttöön myös [palomuuri](palomuuri "wikilink").

### Langaton eli WLAN

Kirjoittajaa kaivataan...


