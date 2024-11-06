## Koodin keskeiset osat ja niiden kommunikointi keskenään

#### HomeController:
IActionResult Product-metodi hakee tiedot tuotteista kutsumalla yksityistä metodia GetProducts(), joka lukee tuotteet JSON-tiedostosta `wwwroot/products.json` ja deserialisoi tiedot listaksi Product-olioita, jotka palautetaan näkymälle.
Kun selaimessa siirrytään Product-metodia käyttävälle sivulle, näkymä saa käyttöönsä products.json-tiedoston tietojen perusteella rakennetun tuotteiden listan.
 	
#### products.json:
Sisältää tuotelistan JSON-muodossa. Sisältö ladataan HomeController-kontrollerissa ja deserialisoidaan Product-olioiksi.
  
#### Product.cs:
Määrittelee Product-olion rakenteen sovelluksessa. FormattedName- ja FormattedPrice-ominaisuudet tarjoavat kulttuurikohtaisen muotoilun nimikkeiden ja hintojen näyttämiseen.
 	
#### Product.cshtml:
Tuoteluettelon käyttäjälle näytettävä näkymä. Saa Product-oliodatan HomeControllerin Product-metodista, jossa products.json-tiedoston data on deserialisoitu. Muodostaa jokaisen Product-olion tiedoista korttinäkymän, jossa on kuva, nimi, kuvaus ja hinta.
 	
#### _Layout.cshtml:
Määrittelee sivupohjan, jota kaikki näkymät käyttävät. Sisältää navigointivalikon, jossa linkki Products-sivulle.
  
#### site.js:
JavaScript-koodi, joka käynnistyy, kun sivu on ladattu. Muotoilee tuotteiden nimet ja hinnat näkymässä.
  
#### site.css:
Tyylitiedosto, joka määrittelee sivun ulkoasun; .product-grid luo ruudukon, jossa tuotteet esitetään ja .product-card luo yksittäisen tuotteen korttinäkymän.
