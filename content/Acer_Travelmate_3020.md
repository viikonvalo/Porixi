+++
Date = "2021-02-06T17:16:57.448Z"
Title = "Acer Travelmate 3020"
Description = "Acer Travelmate 3020"
Aliases = ["/Acer_3020"]
Luokat = ["Teeitse"]
+++

#### Langattoman verkon asennus

Langattoman verkon ajuri asentuu rajoitettujen ajurien hallinan kautta,
mutta lisäksi kortille pitää antaa "virrat", eli ottaa se
ohjelmallisesti käyttöön. Ilman tätä acer-acpia kortti kyllä asentuu,
mutta ei etsi verkkoja.

Käyttöön ottaminen tapahtuu asentamalla acer-acpi ajuri. Ajurin
kehittäjän sivut löytyvät täältä:
[<http://code.google.com/p/aceracpi/>](http://code.google.com/p/aceracpi/)

Lisää /etc/apt/sources.list tiedostoon seuraavat rivit loppuun

Jos sinulla on Ubuntu Feisty Fawn (7.04) (i386 and amd64) :

```
deb <http://www.mumblyworld.info/ubuntu> feisty main
```

Jos sinulla on Ubuntu Gutsy Gibbon (7.10) (i386 and amd64) :

```
deb <http://www.mumblyworld.info/ubuntu> gutsy main
```

Lisäys tapahtuu kirjoittamalla päätteeseen :

```
sudo pico /etc/apt/sources.list
```

Tämän jälkeen selaa tiedoston loppuun alasnuolella ja kirjoita sopiva
lähde. Tallenna tiedosto painamalla ctrl - x ja valitsemalla Y(es) tai
K(yllä) ohjelman kielen mukaan. Tämän jälkeen komenna :

```
wget <http://www.mumblyworld.info/ubuntu/depot.key> -O- | sudo apt-key add -
```

Muista kirjoittaa myös rivin lopussa oleva - -merkki. Tämä komento lisää
edellä sources.listiin lisätyt lähteet luotetuiksi. Seuraavaksi komenna
päätteessä:

```
sudo apt-get install acer-acpi acerwificontroller
```

Ja hyväksy asennus. Käynnistä kone uudelleen vaikkapa komennolla:

```
sudo reboot
```

Langattoman verkon ilmoittimeen pitäisi nyt syttyä valo jos sellainen
koneessa on ja nm_managerin kautta langattomien verkkojen löytyä.

Lähteenä on käytetty
[<http://code.google.com/p/acer-acpi-deb/>](http://code.google.com/p/acer-acpi-deb/)
ja
[<http://code.google.com/p/aceracpi/>](http://code.google.com/p/aceracpi/)

#### 3D työpöydän käyttöönottaminen

Acer 3020 -kannettavassa on ATI:n x600 piirisarjalla oleva näytönohjain.
Koneella saadaan Compiz toimimaan seuraavasti:

-   Asenna ajuri rajoitettujen ajureiden hallinnasta

<!-- -->

-   Asenna Xgl xserveriksi:

```
sudo apt-get install xserver-xgl
```

-   Käynnistä xorg uudelleen (vaikkapa ctrl-alt-backspace)

Lähteenä käytetty :

[<https://help.ubuntu.com/community/CompositeManager/Xgl>](https://help.ubuntu.com/community/CompositeManager/Xgl)

[<http://www.chr05210084.com/content/install-compiz-fusion-ubuntu-gutsy-using-ati-video-card>](http://www.chr05210084.com/content/install-compiz-fusion-ubuntu-gutsy-using-ati-video-card)
