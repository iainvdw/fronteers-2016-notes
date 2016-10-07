# Fronteers 2016

## Progressive enhancement and CSS - Ire aderinokun

Blogt op bitsofco.de

Meestal is PE toegepast op JS en wordt CSS achterwege gelaten.

State of the web: weinig varieteit in browsers

Graceful degradation heeft problemen tov PE:

* het houdt geen rekening met vershcillende behoeften van verschillende bezoekers
* meestal wordt er alleen op 1 versie terug getest

PE: "Wbe design must mature and accept the developments of the apst several years" - stephen champeon

"The goal of webdesign is not merely to dazzle but to deliver information to the widest audience"

* Browser landschap is veel diverser tov 2003.
* Er zijn meer verschillende browser features met veel diverse verschillen onder ondersteuning
* Meer mensen wereldwijd verbonden met het internet met andere behoeftes

PE for JS:
* JS niet aan
* JS feature niet ondersteund

"Make the website functional without JavaSCript" - Ire

Gebruik Feature detection in JS en polyfill features waar mogelijk.

PE voor HTML:

* Browser snapt semantische betekenis van elementen mogelijk niet.
* Aria roles toepassen op html5 elementen voor browsers / clients die het niet ondersteunen

PE voor CSS:

* Niet ondersteunde regels / properties / values wordt niet toegepast.
* We kunnen niet ondersteunde features niet detecteren
* Er is geen "error" detecting

Oplossingen voor PE in CSS:

* "start with sensible html"
* Peanut first! =D
* "take advantage of the cascade"
* oudere properties voor nieuwe declareren
* prefixed props voor unprefixed
* Mobile first media queries
* "What works on desktop, does not immediately work on mobile. What works on mobile is still usable on desktop"
* Slimme helpers met oudere fallbacks:
* text-center -> table-cell + vam -> flex center
* Last resort: losse stylesheets
* Cut the mustard, check voor features en geef browsers die het ondersteunen geavanceerdere features

Feature detection in CSS:

* @supports feature queries

`@supports ( (foo: bar) and/or (bar: baz) ) {
	/* doe iets */
}`

* 70+% ondersteuning voor feature queries
* Gebruik feature queries als PE ipv een requirement
* Sensible defaults

Het landschap in 2030: "MOAR"

* Meer browsers
* devices
* technologieën
* meer mensen online

"Leave no one behind" - Stephen Champeon

## Hacking the visual Norm - Nadieh Bremer

"I don't start on interactivity until the visual form is found"

Pokemon!

Find the right visual form to visualise data.

Using colors to separate groups can create confusion as the colors themselves might me interpreted as grouping or added value to the group.

Voronois are awesome! Very useful for mouseovers over nodes in chart data. Combined with outer circles you can even be more specific in the mouseover region.

Don't underestime hiding parts of your data that are irrelevant.

"Bat plot" :'D

Experimenteer met verschillende vormen van je data, zoek de juiste vorm, kleuren, methode, layout, sortering, etc.

Check zo vroeg mogelijk of het ontwerp matcht met de uiteindelijke data die je krijgt om een zo efficient mogelijke visualisatie te krijgen.

## How you do what you do is who you are - G Scott Olson
Functionaliteit te gebruiken met 1 hand

Apps die dezelfde API gebruiken

Paper Web gebruikt React + BackBone + TypeScript.

Stylus voor CSS + CSS Modules. Inline styles voor components.

"What parts of the app nead to be **seamless**?

* Niet alles hoeft in hetzelfde framework gemaakt te worden.
* Niet alles hoeft in 1 file gebundled te worden. Losse bundles voor losse features = beter

Beetje het wiel opnieuw uitvinden om bestaande web technieken te bouwen in JS. :\

## Offline, progressive and multithreaded: a peek at the wbe apps of the future - Nolan Lawson
"...not attributed to my employer.." Bla bla. Really MS?

PWA! 

* Service worker
* App manifest
* Push notifications
* IndexedDB

Wat bereiken we met PWA?

HTML5 was een reactie tegen Flash en Silverlight in ~2009. Net op tijd op desktop vlak voor de opmars van mobile.

PWA is een reactie op native mobile apps.

### Offline
Het web is niet goed met offline en multithreaded, juist wel met progressive.
PWA brengt offline en multithreaded naar het web.

Offline-first gaat over snelheid. Niet omdat je in de trein zit, maar omdat data op je device VELE malen sneller is te bereiken dan via het netwerk.

Service worker:

* Cache API voor static data > appcache
* IndexedDB voor dynamische data > localstorage / websql

### Progressive
PE toepassen

"In 2016 it's okay to build a website that doesn't work without JavaScript" Hmm..

Zorg ervoor dat de UX goed is *totdat* er JS is ingeladen om dan de UX te verbeteren.

### Multithreaded
Web workers gebruiken voor data operaties. Losse thread. Laat de single-threaded UI thread alleen de UI updaten zodat er "ruimte" overblijft voor complexe functies.

## Multi-user WebVR - Martin Splitt
WebVR kan toegepast worden voor verschillende doeleinden

* Medisch
* Educatie
* Ontwerp
* Architectuur
* etc.

De VR wereld is enorm verdeeld. GearVR, Vive, Oculus, etc. met allemaal proprietaire content.

WebVR haalt VR naar de browser toe, met uiteraard betere cross-platform support.

Kan toegepast worden met foto's, video's, 3D of een combinatie van de technieken.

WebVR kan gecombineerd worden met real-time communicatie om met meerdere mensen in dezelfde VR omgeving rond te "lopen".

Via WebRTC kan je directe communicatie tussen devices opzetten. Daar is eenmalig een server voor nodig om de devices elkaar te laten vinden, maar zodra er een verbinding is loopt de communicatie direct tussen de devices zonder verdere tussenkomst van server.

TRHEE.js is een library als wrapper bovenop WebGL om het eenvoudig te maken om 3D scenes te maken.

Met gradual loading kan je geleidelijk resources inladen om steeds meer te tonen (wireframe, low-res textures, objecten, hi-res textures, etc)

Mik op 90-100 fps omdat onze ogen meer dan 60 fps zien. Hoger is beter voor beter "realisme" in een simulatie.

De GamepadAPI kan erop aansluiten zodat er besturing toegevoegd kan worden aan een VR omgeving.

Nog geen DOM interactie mogelijk. Zit wel in de planning om op te nemen zodat we via elementen in een VR omgeving interacties aan kunnen gaan met pagina's.

De extremen:

Cardboard

* Statisch
* Geen sensors
* Geen beweging
* Geen handen

Vive

* Positie tracking
* Sensors
* "Handen", je kan dingen vasthouden
* Geen vingers

Mogelijkheden om inputs te integreren:

* Leap Motion
* Myo
* Kinect

## Big data, big impact - Lodewijk Nauta

Not quite sure what to make of this.

## Scaling front-end development - Monika Piotrowicz
"What is a FE developer?"
Valt tussen Design en App Dev, alhoewel de technieken van tegenwoordig steeds meer naar App Dev neigen.

Buggy UI is _de_ reden waarmee je vertrouwen verliest van bezoekers.

Mensen kunnen varieren in skillset in het spectrum tussen design en back-end.

### Building a Craft
* Language styleguides voor HTML CSS en JS
* Consistentie
* Helpt nieuwe mensen onderdeel van het team worden
* Vorm een mening over de keuzes

Helpt je code accountable en predictable te zijn.

Whitespace, naming conventions, architectuur.

Standaardiseren van JS test patterns.

Gebruik linting tools die zich aan die guide houden.

Zorg ervoor dat je guide doorontwikkeld wordt en omarm nieuwe standaarden. Dit moet het voornamelijk makkelijker maken, als je het niet kan forceren, is het misschien niet de moeite waard om te controleren.

Zorg voor code reviews waarbij je je team bewust maakt van de guide en code kwaliteit. Met code reviews en comments kan je discussies en leermomenten delen met het team. Dit bouwt een cultuur van feedback en delen van kennis.

Styleguides hebben nut, mensen willen code schrijven van hoge kwaliteit.

### Pattern Libraries
* Bouw een pattern, pas het op andere plekken toe.
* Niet kopieren plakken, dan is niet onderhoudbaar.

Responsive guidelines voor:

* Breakpoint defaults
* Grids
* Styling
* Behaviour
* Perf standards
* Tooling
* A11y best practices voor inclusiviteit

Het is belangrijk om expertise te delen met je hele team, want niemand in je team weet _alles_ van front-end dev. Hiermee til je elkaar naar een hoger niveau.

### UI Library
* Core patterns
* Opinionated voor specifieke use cases, niet generiek
* Stel een lijst van variaties samen van verschillende patterns met regels wanneer je de ene wel of niet toepast
* Welke patterns willen we standaardiseren?
* Welke moeten we versimpelen?

Why bother?

* solve problems once
* more people contrib
* more time on impactful features

Build -> Review -> Teach -> Build

## Surveying the landscape - Peter Gasston
Het web heeft een risico. Veel interacties in messaging, voice, apps.

Technieken van de web worden gebruikt, afgevangen en doorgestuurd naar apps.

Veel bedrijven gaan app-only.

App gates die de site "blokkeren" en vertellen dat je de app moet installeren.

Ads vertegenwoordingen 9% van de visuele ruimte, maar nemen meer dan de helft van laadtijd en bandbreedte in beslag.

21% van mobile users gebruiken adblockers op het web.

Ad markt loopt in de miljarden qua inkomsten en mogelijk verloren omzet door adblockers.

Start geen website. Individuele websites doen er niet meer toe.
- Evan Williams

400 uitgevers overwegen naar Medium over te stappen ipv een eigen website te runnen.

0.85$ uit elke dollar gaat naar Google en FB ads.

De helft van de mensen die online zijn gebruiken FB.

Leesvoer: 'Upload complete' - The Awl.

In azie meer sommige landen meer inwoners die FB gebruiken dan "het internet".

"Web pages are the slowest content there is"

Instant articles laden 10x sneller dan het web.

Canvas ads laden 10x sneller dan het web.

"Facebook becomes the mobile internet".

## Adapting to input - Jason Grigsby