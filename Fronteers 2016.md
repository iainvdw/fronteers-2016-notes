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
In the beginning the web was formless. We gave it form when the web was made commercial.

Consensual hallucination:
Instead of us having somebody trick us, we trick ourselves. The web never had a fixed canvas.

Break free from your assumptions.

1) Input is exploding
1874: Keyboard
1984: Mouse + GUI
1996: Scrollwheel
2005: Camera's
2007: 

* Multi-touch
* Camera
* Acceleromter
* Proximity
* Light

2008: 

* Trackpad, gestures
* GPS
* Voice control
* Gyroscope + front cam

2011:

* BTLE
* Siri

2012: Nothing new :D

2013: Fingerprint

2014: NFC + Barometer

2015: 3D Touch

2016: Nothing new again!

The pace of change matters, not the amount of changes.

Almost every single year after the release of the iPhone we see new sensors and inputs added to our devices.

Hover on touch devices is coming back with soft-capactive input.

We can no longer make assumptions about input based on screen size or form factor.

Input is exploding, it's a continuum, undetectable and transient.

Instead of trying to detect input, just support the types of inputs that are there. Detecting input when it is used, is too late and unreliable.

Design for multiple concurrent inputs. Input is not binary, multiple inputs can be used at the same time.

Do not disable other types of input when another is used.

Abstract baseline input.

Think of point and select instead of tap and click, as they have specific types of inputs associated with them.

Pointer Events spec normalizes touch, mouse and stylus.

Edge + FF + Chrome support it. Safari opposes. Surprising.

jQuery has Pointer Events Polyfill, PEP.

Think of applying different kinds of inputs in the same way, like using hover and gyroscope to achieve the same effect.

All new kinds of APIs to help us adapt to input.

* Payments
* Autofill
* Camera
* Speech recognition
* Web Bluetooth

The web can win in speed as the inputs and UI needed to interact with these APIs is already present in the browser.

For some people, some types of input are faster than the "regular" types of input. Don't judge the types of input. Adapt to them.

Don't worry about different types of input, don't make erroneous assumptions.

'From a "do not harm" perspective, my hope is that people are going to stop thinking form factors have particular types of input.'

## Cheat sheet to a lean website - Barbara Bermes
People don't like to wait, be resepectful.

Websites are getting bigger, but data is still expensive and latency is high.

Make everybody care about performance.

Feel empowered and encouraged to say no.

Celebrate success! It's a good feeling to have made your website faster and improve its performance.

How long does it take my user to start interacting with my page? Discuss it with the designers / ux team.

Treat speed as a feature!

Wireframe for performance. Perf point system:

* Use webpagetest.org to generate load timelines
* Determine load time importance in the wireframes. Place boxes at certain timeframes
* MPM: Measurable Performance Modules
* Show above the fold asap, but determine importance in loading priority within the visible items. Not everything is equally important (stock tickers, ads, hi-res images, etc)

Use a perf budget. Establish a baseline how fast a website should be loading / performing.

Speed testing tools:

* SpeedIndex
* PageSpeed
* SpeedCurve

Determine critical rendering path.

14k rule: serve the most important content first.

Above the fold styles should go inline.

Use async and/or defer to load js as fast as possible and without render blocking. Scripts at the bottom of the page.

Reduce bytes.

* Minify assets
* Images are biggest win targets
* Encode base64
* Avoid custom fonts or use a loader
* Use compression
* Reduce HTTP requests

Fight latency

* Reduce requests
* mobile has highest latency
* Use CDN's
* Use offline storage
* use HTTP/2 for concurrency and reduced latency.

Use task runnrs to help automate perf issues. Implement in your CI.

Avoid the yo-yo effect. Lose weight, gain weight. Don't optimize perf once and forget about it. Continuously measure perf.

"Browsing should be as simple and fast as turning a page in a magazine"
- Larry Page

## Building responsive CSS components - Zell Liew

How do we build responsive components?

Components should be modular and scalable. But they're buzz words, what do they mean?

### Modular
'Composed of standardized units for easy construction'

* Markup structure
* CSS selectors
* Naming convention
* DRY

### Scalabe
'To adjust in amount according to a fixed scale or proportion'

Scale components proportionally at the same rate.

Use responsive units for typography (rem, vw)

How much do we need to scale?

### Design principles
Principle of repetition. Repetition brings familiarity. 

* Limit number of font-sizes, and repeat them
* We don't need infinite scales. Extrapolate the scales from the design you actually need.
* Use consistent whitespace. Vertical rhythm!

Rem vs Em

Em is a unit of typograhpy equal to the currently specified font-size. Problem with `em` is that it's difficult to wrap your head around.

Rem is equal to root font-size. So 1 Rem is always the same size no matter where you specify it.

Em is a local var, Rem is a global var. Local vars are good, Global var is bad. 

Use `em` when it's relative to a font-size, otherwise use `rem`.

Using lots of media queries leads to complication.

Use sensible defaults for base components and apply modifiers for components in different contexts. But even that is not very scalable as modifiers have to be applied manually based on placement.

### Element queries
Media queries query the size of the viewport. Element queries query the size of the component itself.

Not really supported yet, so should be polyfilled with JS.


It's not really about you wanting to scale your components. Talk to your designer and discuss what makes sense.

Extract base styles from components, and use them as mixins in various contexts to avoid repetition.

### Summary
* Make component area maps
* Implement changes early and see what happens instead of changing the design time after time 
* Determine breakpoints and changes in styles
* Determine units for CSS properties
* Establish a line of communication between front-end and design and discuss changes and solutions
* Handle complex variations with mixins or elem queries
* **Don't over-engineer**

Use vertical rhythm (baseline) helper classes to help with scaling, repetition.

Take localization in the design process, compensate for different word or sentence lengts in the design process when your project has to be localized.

