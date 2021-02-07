+++
Date = "2021-02-06T17:16:58.140Z"
Title = "Anturit"
Description = "Anturit"
Luokat = ["Teeitse"]
+++

Lämpötila- ja muut anturit
--------------------------

Debian GNU/Linux versiossa 5.0 ja Ubuntu versiossa 8.10 — 10.04
asennetaan paketti **lm-sensors**. Sitten pääkäyttäjän oikeuksilla
suoritetaan komento **sensors-detect**, eli Debianissa roottina ja
Ubuntussa **sudo sensors-detect**. Tämä komento kyselee kovasti paljon,
vastaa vain myöntävästi kaikkiin. Huomaa viimeisenä kysyttävän haluatko
lisätä tarvittavat ytimen moduulit automaattisesti tiedostoon
/etc/modules, tässsä oletusvastaus on ei, eli pelkkä Enterin painallus
vastaa väärin. Tai sitten joudut lisäämään rivit tiedostoon itse.

Nyt voi komennolla **sensors** kokeilla saadaanko mitään mittaustuloksia
näkyviin. Jos toimi, voi alkaa asentamaan mittaria työkalupalkkiin tai
muualle näkyviin.

### Gnome-työpöytäympäristö

Paketissa **sensors-applet** on Gnomen tehtäväpalkissa näkyvä
pikkusovellus joka osaa näyttää antureista saatuja mittaustuloksia.
Lisäämällä paneeliin "Laitteistoantureiden valvonta" saat sen näkyviin.
Kannattaa katsoa onko arvot järkeviä, ja poistaa ne mittarit joiden
näyttämä on pielessä, silloin ohjelma ei osaa skaalata anturin
mittauksia oikein tai on jotain muuta pielessä.


