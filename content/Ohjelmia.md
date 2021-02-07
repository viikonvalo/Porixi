+++
Date = "2021-02-06T17:17:18.967Z"
Title = "Ohjelmia"
Description = "Ohjelmia"
Luokat = []
menu = ["teeitse"]
weight = 800
+++

Jaettavia ohjelmia, laskentataulukoita yms.
===========================================

Tästä löytyy Porixilaisten tekemiä tiedostoja, joiden käyttöoikeus on
vapaa eli esimerkiksi GNU GPL:n tai Attribution-Share Alike 3.0 Unported
mukainen.

Massapostitus
-------------

Jos pitää lähettää sama sähköposti useille vastaanottajille, voi
menetellä seuraavasti:

1.  kirjoitetaan vastaanottajien sähköpostiosoitteet tekstitiedostoon
    **postios-luettelo.txt** yksi osoite per rivi
2.  kirjoitetaan lähetettävä viesti tekstitiedostoon, esimerkiksi
    **viesti.txt**
3.  mahdolliset liitteet pistään omiin tiedostoihinsa, esimerkiksi
    **liite.pdf**
4.  kirjoitetaan alla oleva tiedostoon, esimerkiksi nimelle
    **postitus.sh** ja tehdään **chmod a+x postitus.sh**
5.  käynnistetään lähetys komentamalla **./postitus.sh**

<!-- -->

```
#!/bin/bash

export EMAIL=omaosoite@jotain.fi
export REPLYTO=omaosoite@jotain.fi
for o in `cat postios-luettelo.txt` ; do
  echo "Lähetetään " $o
  mutt -s "Otsikko tähän" -a "liite.pdf" < viesti.txt $o
  sleep 5
done
```
Komentotiedostossa EMAIL on oma sähköpostiosoite, se minkä haluaa
näkyvän lähettäjän osoitteena. REPLYTO on se osoite, johon toivotaan
vastauksien tulevan. Nämä kaksi osoitetta voivat olla sama.

Kassakirjapohja
---------------

Laskentataulukko, jolla kahvila tms. pitää kassakirjaa. Merkitään päivän
rahaliikenne ja lasketaan päivä ja kalenterikuukauden summat ja saldot.

Kassakirjan tarkoitus: kun kassa lasketaan päivän päätteeksi, katsotaan
kassakoneen kuitista tulot ja menot, ne merkitään kassakirjan
sarakkeisiin. Tässä taulukossa pankkikorttimaksut vähennetään
kassasaldosta koska pankkikorttimaksu menee suoraan pankkitilille eikä
näy kassassa olevassa käteisessä. Kassakirja siis laskee vain kassassa
olevaa käteistä rahaa, jota joka päivän lopuksi verrataan käsin
laskettuun kassaan. Kuun lopuksi toimitetaan kirjanpitäjälle kuukauden
kassakirja tiedostona tai paperille tulostettuna.

Laskentataulukossa on suojattuja soluja, jotta ei vahingossa sotke
otsikkotekstejä yms.. Suojauksen salasana on tyhjä, jotta oikeasti
halutessaan voi kuitenkin muuttaa taulukkoa.

[Media:Lötjösen_kassa_2009.ods.gz‎](/images/Lötjösen_kassa_2009.ods.gz)

Vapaat ohjelmat -esitys
-----------------------

Esityskalvot aiheesta "Mistä avoimessa lähdekoodissa on kysymys". Esitys
on pidetty Turussa AOP:ssä vuonna 2005.

[Media:Vapaat_Ohjelmat.pdf](/images/Vapaat_Ohjelmat.pdf)

--Taleman 18. syyskuuta 2009 kello 08.00 (UTC)

Etävarmistus
------------

Bash-scripti jolla kopioidaan halutut etäkoneen hakemistot
varmistuskopiokoneelle. Tämän komentotiedoston erityisen hienoja
ominaisuuksia on, että se käyttää rsync-komentoa jolloin varmistuskopion
ottaminen nopeutuu huomattavasti. Lisäksi levytilaa säästyy, kun
käytetään rsync-komennon tarkenninta --link-dest, eli semmoisista
tiedostoista joista täsmälleen sama tiedosto on jo levyllä tallennetaan
vain linkki.

Ensimmäisellä kerralla kopioitaessa rsync ei nopeuta yhtään. Jos yhteys
on kovin hidas voi olla tarpeen tuoda ensimmäinen varmuuskopio
etäkoneesta tennariverkolla, eli käy etäkoneen luona tallentamassa
sopivalle taltiolle varmuuskopio ja kantaa sen taskussaan
varmuuskopiokoneelle.

Komentotiedosto ja sen käyttöohje on saatavilla tiedostossa
[Media:Etävarmista.tar.gz](/images/Etävarmista.tar.gz)

--Taleman 23. marraskuuta 2010 kello 17.51 (EET)
