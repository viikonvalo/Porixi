+++
Date = "2021-02-06T17:17:01.654Z"
Title = "ATI rv280"
Description = "ATI rv280"
Luokat = ["Teeitse"]
+++

ATI rv280 -piirisarjallisen näytön-ohjaimen asennus
---------------------------------------------------

Tämä ohje kertoo ATI rv280 piirisarjalla olevan näytönohjaimen
asennuksen puhtaaseen U/Xbuntu asennukseen.

Jos olet tekemässä asennusta vanhaan ubuntun asennukseen varmista että
fgrlx ajuri _ei_ ole käytössä:

```
sudo apt-get remove --purge xorg-driver-fglrx
```

Tarkista vielä xorg.conf että siellä on Devices kohdassa n-ohjaimelle
"ati" -ajuri:

```
grep -i driver /etc/X11/xorg.conf
```

Jos tulosteessa lukee ati niin asia ok. Jos tulosteessa lukee jotain
muuta (kuten vesa tai fglrx) niin aja seuraava komento, joka säätää
xserverin perusasetukset kuntoon:

```
sudo dpkg-reconfigure xserver-xorg
```

Valitse n-ohjaimen ajuriksi "ati"

Olen huomannut asentaessani muutaman kerran Ubuntun ja Xubuntun
sellaiseen koneeseen missän on näytönohjaimena ATIn Radeon 9200 (rv280),
että näytönohjain ei asennu oikein ja 3D-kiihdytys ei ole käytössä.

Voit tarkistaa onko 3D -kiihdytys käytössä kirjoittamalla päätteeseen:

```
glxinfo | grep direct
```

Jos komento tulostaa : "Direct rendering: No" sinulla ei ole 3D
-kiihdytys käytössä.

Ubuntu 7.10 ei jostain syystä suostu asentamaan tätä korttia oikein
ilman seuraavien ohjelmien uudelleen asennusta: libgl1-mesa-gls ja
libgl1-mesa-dri. Asenna ohjelmat uudestaan loitsimalla päätteeseen:

```
sudo apt-get update
sudo apt-get install --reinstall libgl1-mesa-glx libgl1-mesa-dri
```

Ja lisää /etc/X11/xorg.conf tiedostoon seuraavat rivit, jos niitä ei
siellä jo ole:

-   Module sectioon (lisää tämä ylimmäiseksi jos sitä ei vielä ole):  
    ```
    Section "Module"
        load "dri"
    EndSection
    ```
-   Device sectioon:  
    ```
    Section "Device"
        Driver          "ati"
        Option          "UseFBDev"             "true"
        Option          "AccelMethod"          "exa"  # muuta exa xaa:ksi jos on epävakaa
        Option          "AGPFastWrite"         "true"
        Option          "AGPMode"              "4"    # laita tähän agp-väylän kerroin (1-8)
        Option          "EnablePageFlip"       "true" # tämän pitäisi nopeuttaa, mutta joissain tapauksissa kaataa systeemin, kokeile?!
    EndSection
    ```
-   Tiedoston loppuun:  
    ```
    Section "DRI"
           Mode 0666
    EndSection
    Section "Extensions"
           Option "Composite" "Enable"
    EndSection
    ```

Muokkaa tiedostoa /etc/modules ja lisää sinne rivi

```
dri
```

Käynnistä x uudestaan ctrl-alt-backspace.

Nyt tulosteen

```
glxinfo | grep direct
```

pitäisi antaa Direct rendering: Yes

Lähteenä käytetty:

[<http://xorg.freedesktop.org/archive/X11R7.0/doc/html/radeon.4.html>](http://xorg.freedesktop.org/archive/X11R7.0/doc/html/radeon.4.html)

[<https://help.ubuntu.com/community/RadeonDriver>](https://help.ubuntu.com/community/RadeonDriver)

[<http://dri.freedesktop.org/wiki/Building>](http://dri.freedesktop.org/wiki/Building)
