+++
Date = "2021-02-06T17:17:41.080Z"
Title = "Vinkkejä"
Description = "Vinkkejä"
Luokat = []
menu = ["teeitse"]
weight = 1100
+++

Hyödyllisiä vinkkejä sekä tiedon jyväsiä
----------------------------------------

1.  Jotta Linux-jakelu voisi tunnistaa laitteen, pitää jakelun olla
    uudempi kuin laite. Jakelun julkistamisen jälkeen markkinoille
    tulleita laitteita ei jakelun automatiikka pääsääntöisesti voi
    tunnistaa. --[tale](/käyttäjä/Taleman "wikilink") 13. maaliskuuta
    2008 kello 15.20 (EET)
2.  LibreOfficen Writer härnää kirjoittajaa arpomalla jonkin
    samanalkuisen sanan parin merkin kirjoittamisen jälkeen. Tämän
    massatuhoaseen saa onneksi nuketettua valikosta Työkalut |
    Automaattinen korjaus | välilehdellä Sanan täydennys poistamalla
    täpän kohdasta
    &#9633; Sanojen täydennys. --[tale](/käyttäjä/Taleman "wikilink") 25.
    maaliskuuta 2008 kello 10.13 (EET)
3.  Jos kiintolevyn pääkäynnistyslohko on sekaisin, korjaus ehkä [tällä
    ohjeella](http://wiki.ubuntu-fi.org/Grub-kaynnistyslataaja) tai jos
    käytössä on GRUB2 niin [englanninkielinen Grub2 ohje Ubuntun
    wikistä](https://wiki.ubuntu.com/Grub2).
4.  Laitteiston lämpötila- ja muiden anturien mittaamat arvot saa
    näkyviin seuraamalla sivun [Anturit](/Anturit "wikilink") ohjeita.
5.  Kiintolevyn sekaisin menneen **osiotaulun** saa korjattua ohjelmalla
    [Partition Table Doctor](http://www.ptdd.com/). Ohjelma ei ole vapaa
    eikä edes toimi Linuxissa, mutta saatavilla on ilmainen versio,
    jolla voi korjata myös Linux-osioita. Linux-ohjelma on
    [testdisk](http://www.howtoforge.com/data_recovery_with_testdisk).
6.  Mikä Linux-jakelu on käytössä? Tätä voi selvittää seuraavilla
    tavoilla, toivottavasti joku tepsii:
    1.  Komento **lsb_release -a** näyttää, mikäli komento on
        asennettu, esimerkiksi paketista **lsb-release**
    2.  Katsotaan tiedostoa /etc/issue, esimerkiksi **cat /etc/issue**
    3.  Katsotaan tiedostoja /etc/lsb\*, esimerkiksi '''cat
        /etc/lsb_release
    4.  Katsotaan tiedostoa /etc/redhat-release, esimerkiksi **cat
        /etc/redhat-release**
    5.  Katsotaan onko lupaavasti nimettyjä tiedostoja, **ls -lhd
        /etc/\*versio\* /etc/\*release\* /etc/\*issue\***
    6.  Katsotaan onko tiedostoa /proc/version, esimerkiksi **cat
        /proc/version**
    7.  Jos mikään yllä olevista ei anna vinkkejä, ytimen tiedoista ehkä
        löytyy johtolankoja, komento **uname -a**  
        --Taleman 15. toukokuuta 2009 kello 08.00 (UTC)
7.  Ohje, joka neuvoo miten muotoillaan kysymykset semmoisiksi että
    saadaan hyviä vastauksia: [How To Ask Questions The Smart
    Way](http://catb.org/esr/faqs/smart-questions.html). Sivulla
    luvataan suomennoksenkin olevan olemassa, mutten löytänyt sitä
    mistään. Jos sen jostain saa kaivettua, voin tarjota sille uuden
    kodin netistä. --Taleman 23. toukokuuta 2009 kello 08.00 (UTC)
8.  Elokuvakatselimet osaavat ottaa X Windown näytönsäästäjän pois
    päältä. Tämä tuntuu joskus jämähtävän ja näytönsäästäjä ei enää
    käynnistykään elokuvan loputtua. Korjaus komennolla **xset s on**
    (tai käynnistämällä X Window uudelleen, eli kirjautuminen ulos ja
    takaisin sisään tai koneen boottaus).
9.  Suomenkielisiä asiakirjamalleja: [Asiakirjamalleja ja
    esimerkkejä](http://fi.libreoffice.org/ohjeet/mallit/). Toimivat
    LibreOfficen sovelluksissa.
10. LibreOffice Writerissa saa haluamansa muotoilut ja asetukset
    oletusarvoksi tekemällä mallineen jossa halutut asetukset,
    tallentamalla mallineen ja määrittämällä sen oletusmallineeksi.
    Mallin teko neuvotaan kohdassa
    [TK-Tekstinkäsittely](/TK-Tekstinkäsittely "wikilink").
    Oletusmalliksi asettaminen: Tiedosto | Mallit | Järjestä, valitaan
    haluttu malli ja Komennot-painikkeella löytyy Aseta oletusmalliksi
    -toiminto. --Taleman 14. huhtikuuta 2010 kello 14.35 (UTC)
11. Sähköpostia lähetettäessä pitää lähtevän sähköpostin palvelimeksi
    pistää *sillä hetkellä* käytettävän Internet-palvelun tarjoajan
    sähköpostipalvelin. Tämä on tarpeen, koska sähköpostipalvelin huolii
    välitettäväkseen vain omilta asiakkailta tulevia posteja. Jos
    asetuksia ei halua muokata, voi käyttää webmailia, sillä voi
    sähköpostitella vaikka olisi toisen palveluntarjoajan verkon kautta
    Internetissä.
12. ISO-otoksen eli levykuvan liittäminen onnistuu Linuxissa tai
    Unixissa kätevästi näin:

    `# losetup /dev/loop0 /polku/siihen/ISO-tiedostoon/tiedosto.iso`

    `# mount -r -t iso9660 /dev/loop0 /mnt/cdrom`

13. ISO-otoksen saa tehtyä CD-levystä katsomalla ensin komennolla
    isoinfo mikä on CD:n locigal block size ja volume size. Nämä numerot
    pistetään dd-komennolle bs ja count parametrien arvoiksi. Siis

    `# isoinfo -d -i /dev/cdrom`

    `# dd if=/dev/cdrom bs=2048 count=285659 of=/tmp/levynnimi.iso`

14. Miniläppärissä tai muuten pienellä näytöllä saattaa tärkeää tekstiä
    tai jopa tarvittava toimintopainike jäädä näkymättömiin näytön
    reunan ulkopuolelle. Tästä selviää siirtämällä ikkunaa, Alt pohjaan
    ja hiiren ykköspainikkeella vedetään ikkunaa.
15. **T-laskun asennus Debian GNU/Linuxissa:** Asenna paketit
    libqt4-sql-sqlite build-essential libqt4-dev. Nouda TAR-paketti
    osoitteesta <http://helineva.net/t-lasku/>, 32-bittinen tai
    64-bittinen (katso komennolla `dpkg --print-architecture`); pura se
    komennolla tar xvzf *tiedosto*.tar.gz; vaihda hakemistoon johon
    purit tiedostot ja komenna `make all`. Sitten roottina komennat
    `make install` ja asennus on valmis.
16. **Liian suuren .iso -tiedoston polttaminen CD:lle:** Ubuntun
    levyotokset ovat suurempia kuin CD-levylle virallisesti mahtuu.
    Käytettäessä komentoa `wodim` CD:lle kirjoittamiseen, on lisättävä
    tarkennin -overburn. Komento on siis

    `wodim -eject -overburn ubuntu-12.04.2-desktop-amd64-finnishremix.iso`

    **Tämä ei riitä enää 14.04 Ubuntussa!** Nyt levyotos on niin suuri
    ettei se mahdu CD:lle edes overburnin kera. Pitää olla DVD-levy
    jolle kirjoitetaan. Tai tarpeeksi iso USB-muistitikku. LUbuntu
    mahtuu vielä 14.04:ssäkin CD:lle.

17. **Vahingossa poistetut valokuvat** voi yrittää pelastaa ohjelmalla
    **photorec**. Flash-muisteilla se toimii oikeinkin hyvin, koska
    niissä muistisolut käytetään uudestaan vasta kun käyttämättömiä
    soluja ei ole. Saattaa onnistua valokuvan palautus vaikka se on
    poistettu aikoja sitten. Photorec tulee Ubuntussa ja Debianissa
    asennuspaketista testdisk.
18. **Tiedostojen pelastusta** voi yrittää myös **ddrescue**:lla.
    Debianissa ja Ubuntussa se tulee paketissa gddrescue. Tiedostojen
    undeletea voi yrittää myös **testdisk**:llä, muita undelete-tapoja
    neuvotaan [tässä
    artikkelissa](http://www.linux.org/threads/undelete-files-on-linux-systems.4316/).
19. **Lubuntussa** saattaa **työpöytä** mennä **sekaisin**, eli
    paneelista katoaa ohjelmien käynnistimet tai koko paneeli. Korjattua
    saa temppuilemalla käyntiin GUI-istunnossa päätteen. Tämä voi olla
    vaikeaa jos käynnistin puuttuu, kokeile näppäilemällä Control-Alt-T.
    Jos tuolla ei pääteikkuna ilmaannu, lisää paneeli ja paneeliin
    käynnistin lxterminaalille. Sitten pääteikkunassa komennetaan

    `rm -rf ~/.config/lxpanel`

    `lxpanelctl restart`

    Tämän neuvoi \#ubuntu-fi irkissä Mikaela 2014-10-30.

20. Edellisessä vinkissä mainitun ilmiön **voi estää Lubuntussa**
    poistamalla käyttäjältä kirjoitusoikeuden lxpanelin
    asetustiedostoihin. Tämä tehdään komentamalla

    chmod -R a-w \~/.config/lxpanel

21. Kun komennolla **wodim** kirjoittaa RW-levylle, pitää levy ensin
    tyhjentää. Tämä tehdään irroittamalla ensin CD ja sitten
    komentamalla **wodim blank=fast**. Lisää tyhjennysvaihtoehtoja saa
    komennolla **wodim -blank=help**. Tähän tapaan (tarkista käyttäväsi
    oikeaa levylaitteen nimeä!):

    umount /media/cdrom0

    wodim -blank=fast

22. Jos Calc (tai muu taulukkolaskin, ehkä Excel potee samaa?) tulostaa
    tyhjiä sivuja, pistä Näytä-valikosta päälle "Sivunvaihtojen
    esikatselu". Näin näkee mihin Calc on pistänyt pakotetun
    sivunvaihdon. Sitten sen sivunvaihtokohdan voi hiirellä tarttumalla
    siirtää reunaan, jolloin se "katoaa". Mielestäni sitä ei muuten saa
    poistettua.
23. **umask GUI-sovelluksille** saadaan käyttäjäkohtaisesti
    kirjoittamalla tiedostoon `~/.xsessionrc` umaskin asetus,
    esimerkiksi näin:

    `umask 0002`

    Nähtävästi tuon tiedoston suorittava ohjelma ei ole bash, joten ei
    voi käyttää [bashin helpompaa umaskin
    syntaksia](https://en.wikipedia.org/wiki/Umask#Setting_the_mask_using_symbolic_notation).

24. **Sambassa "umask"** eli vastaava kuin edellisessä kohdassa tehty
    asetus jotta käyttäjien luomat tiedostot saa sopivat oikeudet
    tehdään kirjoittamalla tiedostopalvelimessa jossa Sambaa ajetaan
    tiedostoon `/etc/samba/smb.conf` rivit

    create mask = 0774

    directory mask = 0775

    tai tekee nuo samat asetukset Samban selainkäyttöliittymällä
    globaalisti tai siihen tiedostojakoon jossa tuo halutaan voimaan.

25. **Asennus USB-tikulta** tehdään valmistamalla ensin USB-tikku jolta
    asennin käynnistetään. Katso ohje sivulta
    [Asennus_USB-tikulta](/Asennus_USB-tikulta "wikilink")
26. **Työpöytäympäristö** on se järjestelmän osa joka tekee graafisen
    käyttöliittymän. Näitä on Linuxissa useita tarjolla, mutta jakelut
    tapaavat asentaa vain yhden. Ainakin yleiskäyttöisissä jakeluissa
    voi asentaa muitakin työpöytäympäristöjä joista käyttäjä voi valita
    haluamansa sisäänkirjautumisruudussa. Ubuntun ohjeissa on lyhyt
    esittely muutamasta yleisimmästä työpöytäympäristöstä eli [Desktop
    Environmentista](http://askubuntu.com/questions/65083/what-kinds-of-desktop-environments-and-shells-are-available).
27. **Displayport ja DVI/HDMI** kaapelit toimivat vain jos
    tietokoneeseen päin on DisplayPort ja näytössä DVI tai HDMI. DVI:tä
    ja HDMI:tä ei voi muuttaa DisplayPort -signaaliksi pelkällä
    kaapelilla, tarvitaan aktiivikomponentti muuttamaan signaalia. En
    löydä autoritatiivista julkaistua lähdettä tälle tiedolle, mutta
    näin minulle ovat asiaa tietävät vakuuttaneet.
28. **Mihin katosivat ikkunan kehykset?** Näppäimellä F11 saa aktiivisen
    ikkunan kokoruutuun, jolloin ikkunan kehykset mukaan lukien
    painikkeet josta ikkuna pienennetään työkalupalkkiin, suurennetaan
    tai suljetaan katoavat. Saat kehykset takaisin painamalla uudestaan
    F11.
29. **Selain ei käytä oikean reunan tekstiä** jos olet suurentanut
    tekstiä liikaa. Koita painaa Control-0, eli Control-Nolla, se
    palauttaa zoomaustason normaaliksi. Tekstiä saa suurennettu
    näppäilyllä Control-+ ja piennennettyä näppäilyllä Control-- eli
    Control-miinusmerkki.
30. Tähän seuraava vinkki lisää
