+++
Date = "2021-02-06T17:17:15.811Z"
Title = "Millainen kone"
Description = "Millainen kone"
Luokat = []
menu = ["teeitse"]
weight = 500
+++

Tietokoneelle pitäisi helposti saada Linux asennettua ja Linuxin pitäisi
toimia siinä kunnolla.

Vähimmäisvaatimukset
--------------------

Hitain kone johon vuonna 2004 asensin Debian GNU/Linuxin oli 120MHz
Pentium jossa oli 32M muistia. Siinäkin toimi X Window, webbiselaimena
oli Opera ja ikkunointiohjelmana icewm. Ei kannata käyttää
työpöytäympäristöjä kuten Gnome tai KDE näin hitaassa koneessa.

Jos ei käytä graafista ympäristöä, tämmöinenkin kone kelpaa aivan hyvin
komentoriviltä käytettäväksi tai pikku palvelimeksi.

Sopivan tehoinen
----------------

Jos prosessori on 1 GHz tai enemmän, ja muistia ainakin 512 Mt, pitäisi
uudenkin Linuxin toimia kohtuullisesti. Jos jättää työpöytäympäristön
(eli Gnome ja KDE) pois, pitäisi koneen toimia ihan sutjakastikin.

Kannettavat
-----------

Kannettaviin eli läppäreihin saattaa Linuxin asentaminen olla
hankalampaa kuin pöytäkoneisiin. Kannettavissa saattaa olla erikoisosia
tai valmistajan omatekemiä komponentteja. Vaikka Linux asentuisikin
läppäriin, voi olla etteivät erikoisominaisuudet toimi. Esimerkiksi
sähkönsäästöominaisuuksia ei ehkä saa Linuxissa käyttöön, jolloin akun
teho ei riitä niin pitkään kuin siinä käyttöjärjestelmässä joka tulee
läppärin mukana.

Pulma voi olla myös saada ostettua kannettava ilman käyttöjärjetelmää.
Turha maksaa käyttöjärjestelmästä jos sitä ei lainkaan käytä tai joka
tapauksessa heti ottaa koneesta pois. Onneksi [http://linux.fi/
linux.fi](http://linux.fi/_linux.fi "wikilink") ylläpitää luetteloa
[http://linux.fi/index.php/Linux-kannettavat tietokonetoimittajista
jotka myyvät kannettavan ilman
käyttöjärjestelmää](http://linux.fi/index.php/Linux-kannettavat_tietokonetoimittajista_jotka_myyvät_kannettavan_ilman_käyttöjärjestelmää "wikilink").

[Asentelua sivulta](Asennuksista "wikilink") löytyy ohjeita Ubuntun
asentamiseen muutamiin kannettaviin tietokoneisiin.

[Linux on Laptops](http://www.linux-laptop.net/) kertoo merkeittäin ja
malleittain miten Linuxin asentaminen onnistuu. Jos läppäriäsi ei vielä
ole listoilla, kokeile asennusta ja lähetä raportti Linux on Laptoppiin.

Pikkulinuxit
------------

Jotkin Linux-jakelut on tarkoitettu toimimaan hitaissa koneissa ja
pienellä muistilla. [http://damnsmalllinux.com
DSL](http://damnsmalllinux.com_DSL "wikilink") toimii rompulta tai
USB-muistilta käynnistettynä aika vilkkaasti. Erityisesti jos koneessa
on keskusmuistia ainakin 128 Mt, on DSL aivan sikanopea muistiin
asennettuna. Ohjelmat käynnistyvät naks vaan kun ne ladataan
muistilevyltä.

Kokeilin DSL:ää Booksize PC:ssä. Laitteessa on Via Samuel 2 joka on noin
500 MHz suoritin, vastaan 486 suoritinta. Se ei ole järin tehokas mutta
kuluttaa vähänlaisesti virtaa eikä lämpene, eli toimii ilman
tuuletintakin. Muistia on 256 Mt. DSL toimi ihan käyttökelpoisesti,
skanditkin toimii kun muistaa **lang=fi**. Teksturi Beaver tosin ei
siltikään osaa skandimerkkejä, mutta nano osaa.

DSL ei uusissa koneissa oikein toimi, esimerkiksi koneessa jossa on
CD-asema SATA-liitännällä DSL kyllä boottaa rompulta muttei sitten pysty
lataamaan ohjelmiaan rompulta kun SATA-ajuri ei toimi. Ei auttanut
vaikka käynnistysvalitsimeksi lisäsi SATA. DSL käyttää vanhoja
Linux-ytimiä, koska ne ovat pienempiä ja toimivat vanhoissa koneissa
joihin DSL on suunnattu. Uusissa koneissa voi olla oheislaitteita joiden
ajureita ei vanhoissa Linux-ytimissä ole mukana.

Toimivia oheislaitteita
-----------------------

| Laite    | Merkki ja malli   | Jakelu               | Huomautuksia                                                    | Ostopaikka      |
|----------|-------------------|----------------------|-----------------------------------------------------------------|-----------------|
| USB WLAN | TP-LINK TL-WN321G | XUbuntu 8.04 Alpha 6 | Ytimen versiossa 2.6.24 toimii suoraan, aiemmissa kikkailemalla | Mikropasi, Pori |
