+++
Date = "2021-02-06T17:17:06.791Z"
Title = "HP Compaq NX9000"
Description = "HP Compaq NX9000"
Luokat = ["Teeitse"]
+++

#### Näytönohjaimen ajurin asennus

Koneessa toimii kutakuinkin kaikki suoraan, mutta jostain syystä Ubuntu
Gutsyn tavallisessa asennuksessa näytönohjain ei asennu oikein. Jos teet
asennuksen normi asennus levyllä niin X:n käynnistyessa ruudulla näkyy
pelkkää suttua. Tämä saadaa korjattua käynnistämällä kone
vikasietotilassa ja komentamalla päätteessä:

```

sudo dpkg-reconfigure -phig xserver-xorg

```

Valitse näytönohjaimen ajuriksi "ati"

Tämän jälkeen lisätään xorg.confiin seuraava rivi Device kohtaan:

```

`   Option      "LVDSBiosNativeMode" "false"`

```

Ja kaynnistetään kone uudestaan. X:n pitäisi käynnistyä normaalisti ja
näytönohjaimen 3D pitäisi olla käytössä. Näytönohjaimen ajurien oikean
toiminnan voi tarkistaa glxgearssilla ja glxinfolla seuraavasti
päätteessä:

```

glxgears

```

Glxgearssin pitäisi antaa NX9000:llä noin 320fps.

```

glxinfo | grep direct

```

Tämän pitäisi tulostaa : Direct rendering: Yes

#### 3D työpöydän käyttöönottaminen

Otetaan ensin DRI käyttöön komentamalla päätteessä:

```

sudo apt-get update sudo apt-get install --reinstall libgl1-mesa-glx
libgl1-mesa-dri

```

Muuta tämän jälkeen xorg.conf seuraavaksi:

-   Module kohtaan:

```

Section "Module"

`   Load    "dri"`  
`   Load    "extmod"`  
`   Load    "glx"`  
`   Load    "GLcore"`

EndSection

```

-   Device kohtaan:

```

Section "Device"

`   Identifier  "ATI Technologies Inc Radeon IGP 330M/340M/350M"`  
`   BusID       "PCI:1:5:0"`  
`   Driver      "radeon"`  
`   Option      "AGPMode" "4"`  
`   Option      "AGPFastWrite" "true"`  
`   Option      "EnablePageFlip" "true"`  
`   Option      "LVDSBiosNativeMode" "false"   # Tämä poisti kuvan värinän`

EndSection

```

-   Serverlayout kohtaan:

```

`   Option      "AIGLX"     "true"         # työpöytä 3d-kikka-somisteet käyttöön`

```

Tallenna xorg.conf ja lisää vielä /etc/modules tiedostoon seuraavat
rivit:

```

agpgart ati_agp radeonfb radeon drm

```

Käynnistä kone uudelleen. Nyt pitäis olla mahdollista ottaa Compiz
käytöön.

#### TV-outin käyttöönotto

Asenna atitv-out ohjelma:

```

sudo apt-get update sudo apt-get install atitvout

```

Liitä tietokone televisioon s-video kaapelilla ja käynnistä kone
uudelleen. Jostain syystä s-video piuhan tulee olla koneessa kiinni sen
käynnistyessä..?

Ota tv-out käyttöön loitsimalla päätteessä:

```

sudo atitvout -r detect

```

Ohjelma näyttää liitetyt näytöt, tuloksena pitäisi olla jotain
tällaista:

```

Forcing Radeon/Rage 128 mode CRT is attached. TV is attached via
S-Video.

```

Vaihda tila PAL:ksi..

```

sudo atitvout -r pal

```

..ja otetaan TV käyttöön, kuva siirtyy LCD:ltä telkkariin:

```

sudo atitvout -f t

```

Kuvan saa takaisin läppärin näytölle näpyttelemällä:

```

sudo atitvout -f l

```

Lähteenä käytetty:

[<http://forum.ubuntu-fi.org/index.php?topic=13796.0>](http://forum.ubuntu-fi.org/index.php?topic=13796.0)


