# ServerNamingTask

## a)

Päätin hankkia domainnimen sivulleni NameCheapin kautta, koska GitHub Education paketilla sai ilmaisen .me -domainnimen vuodeksi. Tämän toteutin menemällä GitHub Education -sivulle, jossa kirjauduin ja sitten valitsin paketin sisällöstä NameCheapin sivuun johtavan linkin. Täten yhdistin NameCheap käyttäjäni ja GitHub käyttäjäni ja sain kirjoittaa nimen, jonka jälkeen sivu tarkisti, onko nimeä saatavilla. Päädyin tekemään sivun nimellä seikku.me. Aluksi sivu meni GitHub Pagesiin oletusasetuksilla, joten jouduin poistamaan GitHub Pages -repositorioni ja painamaan Unpublish GitHub Pagesissa. Sitten kirjoitin Advanced DNS osioon seuraavat rivit: 

![kuva](https://user-images.githubusercontent.com/105205141/218450488-71062a0f-ec1d-461a-8772-84b9b8a5d429.png)
 
Näillä riveillä määritin että domainnimi menee kyseiselle Digital Ocean palvelimen IP-osoitteelle. Nimen asettaminen kesti noin 1.5h, jonka jälkeen kun yhdistin sivulleni seikku.me, avasi selaimeni oikean sivun tyhjän GitHub Pages -sivun sijasta.

![kuva](https://user-images.githubusercontent.com/105205141/218450701-c59f04f2-090f-4dbc-a598-cfbf355d097f.png)

## b)

Aloitin tutkimiseni seuraavalla komennolla: 

    host seikku.me
   
![kuva](https://user-images.githubusercontent.com/105205141/218451720-8dbb7a0f-b005-4d36-8eda-a4feb7656df7.png)

Host -komennolla sain listaan kaikki ne IP-osoitteet jotka NameCheap oli luonut oletukselta sekä oman DigitalOcean palvelimeni osoitteen (maalattuna). 

Tämän jälkeen latasin dnsutils-paketin voidakseni käyttää dig-komentoa. 

    sudo apt-get install dnsutils
    dig 142.93.103.158 seikku.me
    
![kuva](https://user-images.githubusercontent.com/105205141/218452369-f1c959fa-5f8c-4c68-8951-f8d45d24cc1d.png)
![kuva](https://user-images.githubusercontent.com/105205141/218452439-e581016a-b97b-4a5c-95e3-b1c2991d416b.png)

Dig-komennosta voidaan tulkita palvelimen osoite sekä responsetime DNS-osoitteessa, sekä IP-osoitteessa. 

Jostain syystä minulla Query time molemmissa näytti olevan 0msec.


