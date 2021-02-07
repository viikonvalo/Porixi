+++
Date = "2021-02-06T17:16:59.539Z"
Title = "Asennus USB-tikulta"
Description = "Asennus USB-tikulta"
Luokat = []
menu = ["teeitse"]
weight = 200
+++

Asennusotoksen kirjoittaminen CD-levylle ei enää välttämättä ole paras
tapa tehdä asennnustaltio. Uudet asennusotokset tapaavat olla liian
suuria mahtuakseen CD-levylle. DVD-levylle ne mahtuvat.

USB-tikulla on etuja optiseen levyyn verrattuna, ainakin ne ovat
pienempiä ja helpompia kuljettaa mukana. Nykyään tietokoneetkin osaavat
käynnistyä USB-muistilta, ainakin noin alle 10 vuotta vanhat koneet
tapaavat osata.

ISO-otoksen kirjoittaminen USB-tikulle
--------------------------------------

Tämä tapa toimii ainakin Debianin ja Ubuntun levyotoksille. Ne on
hybridi-otoksia, eli toimii sekä CD/DVD-levylle kirjoitettuna että
USB-tikun kanssa.

-   USB-tikku paikalleen
-   Katso mikä levylaite siitä tuli komennolla:

```
dmesg | tail -20
```

```
[ 2000.648071] usb 6-4: new high-speed USB device number 5 using ehci-pci
[ 2000.781602] usb 6-4: New USB device found, idVendor=0951, idProduct=1666
[ 2000.781608] usb 6-4: New USB device strings: Mfr=1, Product=2, SerialNumber=3
[ 2000.781612] usb 6-4: Product: DataTraveler 3.0
[ 2000.781615] usb 6-4: Manufacturer: Kingston
[ 2000.781618] usb 6-4: SerialNumber: 60A44C413C4EBFA0D9840068
[ 2000.782023] usb-storage 6-4:1.0: USB Mass Storage device detected
[ 2000.782290] scsi5 : usb-storage 6-4:1.0
[ 2001.780753] scsi 5:0:0:0: Direct-Access     Kingston DataTraveler 3.0 PMAP PQ: 0 ANSI: 6
[ 2001.781711] sd 5:0:0:0: Attached scsi generic sg3 type 0
[ 2001.782359] sd 5:0:0:0: [sdb] 15138816 512-byte logical blocks: (7.75 GB/7.21 GiB)
[ 2001.783240] sd 5:0:0:0: [sdb] Write Protect is off
[ 2001.783244] sd 5:0:0:0: [sdb] Mode Sense: 45 00 00 00
[ 2001.783859] sd 5:0:0:0: [sdb] Write cache: disabled, read cache: enabled, doesn't support DPO or FUA
[ 2001.827012]  sdb: sdb1
[ 2001.830108] sd 5:0:0:0: [sdb] Attached SCSI removable disk
```

Tuosta katsotaan levylaite on sdb. Se voi olla joku muukin, eli pitää
katsoa mitä dmesg näyttää sen jälkeen kun USB-tikku on paikallaan.

-   Kirjoitetaan .ISO-tiedosto sille tikulle. Aikaa kuluu noin 4
    minuuttia 1 Gtavun otoksen kirjoittamiseen.

<!-- -->
```
time cp ubuntu-15.10-desktop-i386.iso /dev/sdb ; sync
```

Käyttö
------

Vielä pitää saada tietokone käynnistymään USB-tikulta. BIOS-asetuksissa
voi säätää käynnistymisjärjestyksen. Useissa koneissa BIOS tarjoaa
mahdollisuuden käynnistyksen aikana päästä valitsemaan käynnistyslaite.
Katso ruudulla luvataanko siinä F9, F12 tai jollain muulla
pikanäppäilyllä pääsy käynnistyslaitteen valintaan tai vastaavaan
toimintoon. Tämä on parempi tapa, kun ei tarvitse pysyvästi vaihtaa
käynnistysjärjestystä. Kun tietokoneelle on saatu käyttöjärjestelmä
asennettua ei taideta tarvita käynnistystä muulta kuin sisäiseltä
kiintolevyltä.

Viitteitä
---------

Tarkempi selostus löytyy Debian GNU/Linuxin asennusohjeesta luvusta
[4.3. Preparing Files for USB Memory Stick
Booting](https://www.debian.org/releases/stable/amd64/ch04s03.html.en).
