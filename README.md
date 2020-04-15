# Challenge-3-XT2-Justin

https://jvw17.github.io/Challenge-3-XT2-Justin/

<b>In het kort:</b> voor deze challenge heb ik een soort dashboard gemaakt voor de Marsbewoners die terugkeren naar de aarde. In het dashboard kunnen ze een land intikken om vervolgens meer informatie te krijgen over dat land. Zo is algemene informatie over het ingevoerde land te lezen, is de vlag te zien en het weer in de hoofdstad van dat land. De gebruiker hoeft niet de volledige naam van het land in te tikken, een deel van de naam is al voldoende.

<b>Even uitgebreid:</b> mijn website maakt gebruik van de volgende twee API's:

1. <b>REST Countries</b>, https://restcountries.eu/<br/>
Deze API haalt een hele rits aan informatie op over het ingevoerde land (wat naast de webpagina ook steeds in de console terug te vinden is). Ik heb een deel van deze opgehaalde informatie weergegeven onder het kopje 'Country information,' het onderste blok op de pagina. Ik heb geprobeerd om nuttige informatie weer te geven over het land voor de Marsbewonders, zodat deze meer te weten kunnen komen over het land waar ze mogelijk willen landen. Zo kunnen deze erachter komen... <br/>
 ... wat de naam van het land is in de taal die gesproken wordt in het land (Native name, zo krijgen de Marsbewoners een indruk van de  taal die er gesproken wordt). <br/>
... waar het land ongeveer op aarde ligt (Region en Subregion). <br/>
... wat de hoofdstad is (Capital). <br/>
... welk betaalmiddel in het land gebruikt wordt en wat het symbool daarvan is (Currency + symbol, handig als de Marsbewonders iets willen kopen in het land). <br/>
... hoeveel mensen in het land wonen (Population). <br/>
... hoe groot het land is (Area in km²). <br/>
... wat het landnummer is (Calling Code, handig voor als de Marsbewoners naar iemand willen bellen in het land. Zo weten ze welk nummer ze eerst voor een telefoonnummer in moeten toetsen. Bij Nederland is dit bijvoorbeeld 31). <br/>
... wat de vlag van het land is. Deze is te zien onder het kopje 'Flag of the country'.

2. <b>OpenWeather (heel origineel, ik weet het)</b>, https://openweathermap.org/current <br/>
Deze API haalt informatie op over het weer in de hoofdstad van het ingevoerde land. Hoe werkt dat precies? Deze API is gekoppeld met de andere API. Nadat de gebruiker een (deel van een) land heeft ingetikt in de zoekbalk, haalt de REST Countries API de data op van het ingevoerde land. Daarbij wordt ook de hoofdstad opgehaald. In mijn JS code in regel 30 is terug te vinden dat ik een variabele heb gemaakt waarvan de waarde de opgehaalde hoofdstad is. Deze variabele heb ik geplaatst in de URL die opgehaald moet worden door de OpenWeather API (regel 37). <br/>
<b>Oftewel:</b> de OpenWeather API haalt de hoofdstad op uit de data die de REST Countries API heeft opgehaald. Vervolgens haalt de OpenWeather API het weer in de hoofdstad op.<br/>
Onder het kopje 'Weather in the capital' is het weer in de hoofdstad te vinden. Er is een plaatje van het weer, temperatuur, beschrijving van het weer en de windsnelheid in km/h. Ik heb voor deze vier weergegevens gekozen omdat ik vind dat de Marsbewonders zich zo voor kunnen stellen wat het weer in de hoofdstad is.

<b>Foutmelding</b> <br/>
Als de gebruiker een typfout maakt of iets invuld dat geen land is, geeft de pagina een foutmelding. Daarbij gebeurt het volgende:
1. De tekst onder het kopje 'Country information' verdwijnt
2. Onder het kopje 'Weather in the capital' verdwijnt de afbeelding van het weer en de bijbehorende tekst. In plaats daarvan verschijnt de tekst: 'Loading...' en 'Please wait.'
3. Onder het kopje 'Flag of the country' verschijnt in het rood de foutmelding 'Please try again. Did you make a spelling mistake?' Deze foutmelding is rood zodat deze extra opvalt.

<b>Algemene informatie over de webpagina</b> <br/>
- De hele webpagina is in het Engels, omdat de twee gebruikte API's hun data alleen in het Engels ophalen. Daarom vond ik het niet verstandig om de webpagina in het Nederlands te maken.
- Als de gebruiker op de zoekknop klikt, wordt deze kort oranje. Dit zodat de gebruiker het idee krijgt dat de webpagina niet vastloopt als deze op de zoekknop klikt en er niks gebeurt.
- Ik wil niet dat de Marsbewoners op Antarctica landen, want daar is het erg koud en onbegaanbaar. Daarom heb ik ervoor gezorgd dat de webpagina geen gegevens laat zien als de gebruiker Antarctica invoert. Tevens is Antarctica een continent en geen land!

