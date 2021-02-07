+++
Date = "2021-02-06T17:17:10.935Z"
Title = "Levyn lisäys"
Description = "Levyn lisäys"
Luokat = ["Teeitse"]
menu = ["teeitse"]
weight = 300
+++

Levyn lisäys
------------

Uuden kiintolevyn lisäämisessä pitää ensin saada levy kiinni koneeseen
ja sitten ottaa levy käyttöön Linuxissa.

### Levyn ruuvaaminen koneesen

Ensimmäiseksi kannattaa levyssä mahdollisesti olevat siltaimet
(jumpperit) pistää paikalleen. Niitä on hankala näprätä sitten kun levy
on ruuvattu tietokoneen levyhyllylle. Jos kyseessä on Sarja-ATA levy, ei
siltaimista tarvitse välittää. Levyn päällä useimmiten lukee mitä
siltaimet tarkoittavat, ja yksi siltainpalikka tapaa olla levyssä kun se
ostetaan. Jos ATA-väylässä on levy tai levyjä, täsmälleen yhden pitää
olla Isäntä (master). Jos levyjä on toinenkin, sen on oltava Orja
(slave). Ei ole väliä kumpi on kumpi, kunhan tuota sääntöä noudatetaan.
Isäntä/Orja asetuksen sijaan voi käyttää Cable Selectiä, jossa paikka
ATA-kaapelissa määrää kumpi on isäntä ja orja. Jos Cable Selectiä
käytetään, kaikkien kaapelissa olevien levyjen on sitä käytettävä.

Kiintolevyjen yleisin koko on 3,5" (oikeasti nelisen tuumaa leveitä),
tietsikassa useimmiten on sopivan kokoinen paikka näille levyille. Jos
ei ole, romppuasemille tarkoitettuihin paikkoihin saa pienemmän levyn
asennusraudoilla (saa tietokonekaupasta). Läppäreissä käytetään 2,5"
kokoisia levyjä.

Kaapelit saa mahdollisesti helpommin kiinni ennen kuin levyn ruuvit
kiinnittää, jos tilat koneen sisällä ovat ahtaat kannattaa miettiä
kokoamisjärjestystä. Levyyn kiinnitetään virtajohto, tulee
virtalähteestä ja syöttää levylle käyttöjännitteen. Jos virtajohtoja ei
ole vapaina, tietokonekaupasta saa haaroittimia. Mahdollisesti kannattaa
miettiä riittääkö virtalähteen teho vielä yhdelle laitteelle. Virtajohto
sopii paikalleen vain yhdellä tavalla, katsele liittimiä niin johto
mennee oikein päin.

#### IDE-levyt

Toinen johto koneeseen on se jota pitkin tieto siirtyy. Emolevyllä tapaa
olla kaksi IDE-liitäntää, käyttöjärjestelmä nimeää levyt järjestyksessä
IDE1:Master, IDE1:Slave, IDE2:Master, IDE2:Slave.

| IDE1 Isäntä | /dev/hda |
|:------------|----------|
| IDE1 Orja   | /dev/hdb |
| IDE2 Isäntä | /dev/hdc |
| IDE2 Orja   | /dev/hdd |

Jos pistät uuden levyn IDE1:Masteriksi mieti osaako kone enää käynnistyä
jos käynnistyslevy ei enää olekaan ensimmäinen. Leveän liittimen
*punaisella merkitty johto tulee sille puolelle jossa levyn virtaliitin
on*. Liitin saattaa sopia molemmin päin, mutta toimii vain jos se on
oikeinpäin.

IDE-levyjen data-kaapeleita eli ATA-kaapeleita on saatavilla pyöreäksi
tehtyinä, jolloin lattakaapeli on leikattu kapeiksi soiroiksi ja
teipattu kapeampaan kimppuun. Liittimet ovat silti leveitä.

#### Sarja-ATA-levyt

Sarja-ATA levyllä liittimet sopivat vain yhtä tietä paikalleen, ja
datakaapeli on kapeampi. Emolevyllä on useita Sarja-ATA eli Serial-ATA
liittimiä, kuhunkin tulee vain yksi levy. Sarja-ATA-levyissä ei
siltaimella tarvitse valita onko levy isäntä vai orja, levyt
tunnistetaan käytetyn emolevyn liittimen mukaan. Tarkista emolevyn
manuaalista mikä liitin on 1, 2, 3 jne.

#### Uudet Linuxit

Nykyään Linuxit saattavat näyttää kaikki kiintolevyt ja muutkin
levyasemat SCSI-levyinä, siis käyttävät SCSI-ajuria levyajurina. Tällöin
levyt näkyvät nimillä /dev/sda, /dev/sdb, /dev/sdc jne. Sarja-ATA levyt
esimerkiksi näkyvät tälläisinä. Oikeat SCSI-levyt näkyvät tietysti myös
tällä tavalla nimettyinä.

Käytä niitä nimiä joita fdisk -l koneessasi näyttää.

### Levy käyttöön Linuxissa

Levy otetaan käyttöön Linuxissa tekemällä levylle osiot, osioon
tiedostojärjestelmä ja liittämällä tiedostojärjestelmä haluttuun
liitoskohtaan.

Ensin katsotaan levyjen nimet komennolla **fdisk -l**. Tästä näkee myös
onnistuiko kaapelien kiinnittäminen, jos uutta levyä ei **fdisk** osaa
näyttää jompi kumpi johto on irti tai huonosti kiinni.

```

wally:\~\# fdisk -l

Disk /dev/hda: 123.5 GB, 123522416640 bytes 255 heads, 63 sectors/track,
15017 cylinders Units = cylinders of 16065 \* 512 = 8225280 bytes

Device Boot Start End Blocks Id System /dev/hda1 1 12085 97072731 83
Linux /dev/hda2 12086 12226 1132582+ 5 Extended /dev/hda4 \* 12227 15017
22418707+ 7 HPFS/NTFS /dev/hda5 12086 12226 1132551 82 Linux swap /
Solaris

Disk /dev/hdd: 203.9 GB, 203928109056 bytes 255 heads, 63 sectors/track,
24792 cylinders Units = cylinders of 16065 \* 512 = 8225280 bytes

Disk /dev/hdd doesn't contain a valid partition table

```

Yllä olevasta huomaa koneessa olevan vanhan levyn nimeksi `/dev/hda`, ja
uuden levyn `/dev/hdd`. Uudelle levylle ei ole levyosioita tehty, siksi
**fdisk** ilmoittaa Disk /dev/hdd doesn't contain a valid partition
table.

Levyosiot voi tehdä esimerkiksi komennolla **cfdisk /dev/hdd**, pitää
kertoa mille levylle osiot tehdään. **cfdisk** toivottavasti on
riittävän helppo käyttää, jos ei ole pitää lukea komennon man-sivu
(**man cfdisk**). Levyosion tyypiksi tulee Linux eli 83 jos levyosiota
on tarkoitus Linuxissa käyttää. Jos tekee levylle myös Swap-osion, sen
tyypiksi tulee 82. Muut mahdolliset tyypit näkee cfdiskin
Type-toiminnolla.

```

wally:\~\# fdisk -l /dev/hdd

Disk /dev/hdd: 203.9 GB, 203928109056 bytes 255 heads, 63 sectors/track,
24792 cylinders Units = cylinders of 16065 \* 512 = 8225280 bytes

Device Boot Start End Blocks Id System /dev/hdd1 1 24792 199141708+ 83
Linux

```

Seuraavaksi tehdään levyosioon tiedostojärjestelmä. Linuxissa on
tarjolla monia erilaisia tiedostojärjestelmiä, mutta jos et tiedä
asiasta mitään käytä ext2, ext3, ext4 tai xfs. Näistä ext2 ei sisällä
tiedosto-operaatioiden kirjanpitoa, sitä ei kannata käyttää usean
gigatavun tiedostojärjestelmille. Mutta ext3, ext4 tai xfs ovat mukavia
satojen gigojen tai teratavujen tiedostojärjestelminäkin
(tiedostojärjestelmän tarkistus ei kestä tuntia, alle minuutin isollakin
levyllä). Haluttaessa tietty tiedostojärjestelmä käyttöön on sen
työkaluohjelmat oltava asennettuna, jotta esimerkiksi
**mkfs.*tiedostojärjestelmä*** löytyy. Myös reiserfs on hyvä, mutta voi
olla ettei sitä jatkossa kehitetä enää.

Tiedostojärjestelmä tehdään komennolla **mkfs**, parametrina annetaan
haluttu tiedostojärjestelmä ja levyosio. Tiedostojärjestelmille voi
muokata erilaisia asetuksia, mutta jos olet niistä kiinnostunut tietänet
itse mitä haluat.

```

wally:\~\# mkfs -t reiserfs /dev/hdd1 mkfs.reiserfs 3.6.19 (2003
www.namesys.com)

A pair of credits: Alexander Lyamin keeps our hardware running, and was
very generous to our project in many little ways.

Joshua Macdonald wrote the first draft of the transaction manager. Yuri
Rupasov did testing and benchmarking, plus he invented the r5 hash (also
used by the dcache code). Yura Rupasov, Anatoly Pinchuk, Igor
Krasheninnikov, Grigory Zaigralin, Mikhail Gilula, Igor Zagorovsky,
Roman Pozlevich, Konstantin Shvachko, and Joshua MacDonald are former
contributors to the project.

Guessing about desired format.. Kernel 2.6.8-2-386 is running. Format
3.6 with standard journal Count of blocks on the device: 49785424 Number
of blocks consumed by mkreiserfs formatting process: 9731 Blocksize:
4096 Hash function used to sort names: "r5" Journal Size 8193 blocks
(first block 18) Journal Max transaction length 1024 inode generation
number: 0 UUID: ec164c27-1502-4832-848a-eabac8797f01 ATTENTION: YOU
SHOULD REBOOT AFTER FDISK! ALL DATA WILL BE LOST ON '/dev/hdd1'!
Continue (y/n):y Initializing journal -
0%....20%....40%....60%....80%....100% Syncing..ok

Tell your friends to use a kernel based on 2.4.18 or later, and
especially not a kernel based on 2.4.9, when you use reiserFS. Have fun.

ReiserFS is successfully created on /dev/hdd1.

```

Huomaa että tiedostojärjestelmä tehdään levyosioon (`/dev/hdd1`) eikä
levylaitteelle (`/dev/hdd`).

Tiedostojärjestelmä voidaan liittää haluttuun kohtaan, tässä tapauksessa
liitoskohta on `/opt/Varmuuskopiot`. Sitten levyosio liitetään
liitoskohtaan komennolla **mount**.

```

wally:\~\# mkdir /opt/Varmuuskopiot wally:\~\# mount -t reiserfs
/dev/hdd1 /opt/Varmuuskopiot/


\~\# df -hT

Tied.järj. Tyyppi Koko Käyt Vapaa Käy% Liitospiste /dev/hda1 ext3 92G
14G 73G 16% / tmpfs tmpfs 189M 0 189M 0% /dev/shm tmpfs tmpfs 10M 772K
9,3M 8% /dev /dev/hdd1 reiserfs 190G 33M 190G 1% /opt/Varmuuskopiot

```

Jos liitoskohdassa on jotain ennestään, niihin tiedostoihin ei pääse
käsiksi ennen kuin liitetty levyosio irroitetaan komennolla **umount**.

### Liittäminen bootissa

Edellä itse tehty liittäminen pysyy kunnes tehdään **umount** tai kone
sammutetaan. Jotta levyosio liitettäisiin tiedostojärjestelmän osaksi
aina koneen käynnistyessä, on tiedostoa `/etc/fstab` muokattava.

```

wally:\~\# cat /etc/fstab

# /etc/fstab: static file system information.
#
#  <file system> <mount point> <type> <options> <dump> <pass>
proc             /proc         proc   defaults  0      0
/dev/hda1        /             ext3   defaults,errors=remount-ro 0 1
/dev/hda5        none          swap   sw        0      0
/dev/hdc         /media/cdrom0 iso9660 ro,user,noauto 0 0
/dev/fd0         /media/floppy0 auto  rw,user,noauto 0 0

# Musacorner
phb:/opt/Varasto/Musa /opt/Musa nfs ro,user,noauto 0 0
```

Tiedostoa muokattaessa on tärkeää katsoa, että riville tulee
*täsmälleen* kuusi kenttää. Muutenkin kannattaa tämä tiedosto kirjoittaa
oikein, vältyt murheelta. Jos kone ei enää käynnisty kun kämmäsit
juuriosion tai muun tärkeän osion liittämisen, käynnistä kone
pelastuslevyltä ja korjaa `/etc/fstab` kuntoon tai ennalleen.

Sarakkeiden merkitykset ovat:

1.  levyosio jolla tiedostojärjestelmä on
2.  liitoskohta
3.  tiedostojärjestelmä (auto tunnistaa)
4.  valitsimet
    -   ro = vain luku
    -   rw = luku ja kirjoitus
    -   user = käyttäjä voi liittää ja irrottaa
    -   noauto = ei liitetä bootissa
    -   auto = liitetään bootissa, oletus
5.  dump = osion varmuuskopiointiin dump-komennolla
6.  pass = missä järjestyksessä tehdään fsck, tiedostojärjestelmän
    tarkistus

Tässä tapauksessa lisättäisiin tiedostoon rivi

```
/dev/hdd1 /opt/Varmuuskopiot auto defaults 0 2
```

mikä vaikkapa katsomalla mallia muista riveistä tai lukemalla
**man fstab** pitäisi selvitä.

```
wally:/etc\# cat fstab

# /etc/fstab: static file system information.
#
# <file system> <mount point> <type> <options> <dump> <pass>
proc            /proc         proc   defaults  0      0
/dev/hda1       /             ext3   defaults,errors=remount-ro 0 1
/dev/hda5       none          swap   sw        0      0
/dev/hdc        /media/cdrom0 iso9660 ro,user,noauto 0 0
/dev/fd0        /media/floppy0 auto rw,user,noauto 0 0

# Uusi 200G levy
/dev/hdd1 /opt/Varmuuskopiot auto defaults 0 2

# Musacorner
phb:/opt/Varasto/Musa /opt/Musa nfs ro,user,noauto 0 0
```

Nyt pitäisi koneen käynnistyessä uusi levy liitettämän osaksi
tiedostojärjestelmää.

#### Uusimuotoinen fstab

Ubuntu Hardy Heron eli versio 8.04 osaa käyttää levyosion UUID:tä
tiedostojärjestelmän tunnisteena laitetiedoston nimen tilalla. Tällöin
tiedosto `/etc/fstab` on tämän näköinen:

```

# /etc/fstab: static file system information.
#
# <file system> <mount point> <type> <options> <dump> <pass>
proc            /proc         proc   defaults  0      0

# /dev/sda2
UUID=e5f0566d-6c97-4617-b3ea-84e68d71f237 / ext3 relatime,errors=remount-ro 0 1
# /dev/sda1
UUID=df501a2a-ea25-441e-bee2-171f049b9950 none swap sw 0 0
/dev/scd0 /media/cdrom0 udf,iso9660 user,noauto,exec,utf8 0 0
/dev/fd0 /media/floppy0 auto rw,user,noauto,exec,utf8 0 0
```

Levyosion UUID:n näkee hakemistosta `/dev/disk/by-uuid/` (näin neuvoi
jjo ircissä kanavalla \#ubuntu-fi). Muita käyttökelpoisia komentoja ovat
`vol_id -uuid laitetiedostonnimi` ja `blkid`. Koska UUID on niin pitkä
ja kryptinen, kannattaa tiedostojärjestelmälle tehdä nimiö eli label.
Komentoja: `mlabel`, `e2label`, `ntfslabel`, `reiserfstune --label=`.

Esimerkki nimiön käytöstä:

```
# Kotihakemistot
LABEL=home /home reiserfs defaults 0 2
```

--[tale](/käyttäjä/Taleman "wikilink") 17. helmikuuta 2008 kello 13.35
(EET)  
--Taleman 17. kesäkuuta 2008 kello 10.47 (EEST)

### Windows-levyn liittäminen

Tästä on oma sivunsa: [Liitä Windows osio](Liitä_Windows_osio "wikilink").
