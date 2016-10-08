# Fronteers 2016

## Progressive enhancement and CSS - Ire aderinokun

Blogs on bitsofco.de

Most of the time PE is applied to JS and CSS hasn't been considered.

State of the web back in 2003: low variety in browsers.

Graceful degradation has problems compared to Progressive Enhancement

* It doesn't take in consideration different needs for different visitors as it degrades to one specific
* Mostly the degradation is tested one browser version back

PE: "Web design must mature and accept the developments of the past several years" - Stephen Champeon

"The goal of webdesign is not merely to dazzle but to deliver information to the widest audience"

* Browser landscape now is much more diverse than in 2003
* The are loads more feature with each of them having different levels of support across the browsers
* More people connected to the internet with different needs
   
PE for JS:

* JS not enabled
* JS feature not supported

"Make the website functional without JavaSCript" - Ire

Use Feature detection in JS and polyfill features where possible.

PE for HTML:

* Browser possibly doesn't understand semantic meaning of newer elements.
* Apply ARIA roles to HTML5 elements so the role can be understood by older clients.

PE for CSS:

* Rules, properties and values that are not supported don't get applied.
* We can't check for not supported features
* There is no error detection in CSS

Solutions for PE in CSS:

* "start with sensible html"
* Peanut first development! =D
* "take advantage of the cascade"
* Declare older properties and values before newer ones.
* prefixed props before unprefixed
* Mobile first media queries
* "What works on desktop, does not immediately work on mobile. What works on mobile is still usable on desktop"
* Use smart helpers with older fallbacks, like for example a text centering helper:
* text-center -> table-cell + vam -> flex center
* Last resort: separate stylesheets for different browsers
* Cut the mustard, check feature support and apply advanced features in newer browsers

Feature detection in CSS:

* @supports feature queries

```css
@supports ( (prop: value) and/or (prop: value) ) {
	/* apply checked feature */
}
```

* 70+% support across browsers for feature queries
* Use feature queries as PE instead of a requirement for something to work. Upgrade it.
* Use sensible defaults

The landscape of the web in 2030: "MOAR"

* More browsers
* More devices
* More technologies
* More people online

> Leave no one behind

— Stephen Champeon

## Hacking the visual Norm - Nadieh Bremer

> "I don't start on interactivity until the visual form is found"

— Nadieh

Iterate through several forms of presenting data until you have found the right format to visualise what you mean clearly.

Nadieh uses D3.js heavily to present data in awesomely designed charts.

Pokemon chart!

Using colors to separate groups can create confusion as the colors themselves might me interpreted as grouping or added value to the group.

Voronois are awesome! Voronois create "cells" around nodes in your chart. Very useful for e.g. detecting mouseovers over nodes in chart data. Combined with outer circles you can even be more specific in the mouseover region to show extra data of the node being hovered over.

Don't underestimate hiding parts of your data that are irrelevant.

"Bat plot" :'D

Experiment with different forms of your data, find the right form, colours, method, layout, sorting, etc.

Check your visual form with real data as soon as possible as mock data might give you a different result. Real data will give you a more efficient view of the end result.

## How you do what you do is who you are - G Scott Olson
Think about the interaction your end user has with your app. Take their needs into consideration. Let the user navigate your app with one hand to make it as user friendly as you possibly can.

The Paper apps all use the same API endpoints to send and retrieve data.

Paper Web uses React + BackBone + TypeScript.

Stylus for CSS + CSS Modules. Inline styles for components.

> What parts of the app nead to be **seamless**? 

Not every part of the app has to be loaded in one monolithic bundle. Page refreshes between certain areas of your app could be very acceptable. Separate your main app logic from liek the user account flow.

Not everythin has to be built in the same framework. You could use server-side frameworks or even static pages to present certain parts of your site/app.

Some demos did look like he was reinventing the wheel of already established techniques, but now solved with JS. Spacer components? Aspect ratios? All could be solved with CSS and HTML.

## Offline, progressive and multithreaded: a peek at the wbe apps of the future - Nolan Lawson
"...not attributed to my employer.." Bla bla. Really MS?

PWA! 

* Service worker
* App manifest
* Push notifications
* IndexedDB

What can we achieve with PWA?

HTML5 was a response to Flash and Silverlight in around 2009. Just in time for the advance of mobile.

PWA is a response to native mobile apps.

### Offline
The web isn't very good with offline and multithreading, but it ís really progressive in contrast to native apps. PWA brings offline and multithreading to the web.

Offline-first is about speed. Not because you're in the train or have crappy WiFi, but because data on your device can be reached much faster in several orders of magnitude compare to the network.

Service worker:

* Cache API for static data is better than appcache
* IndexedDB for dynamic data is better than LocalStorage or the deprecated WebSQL

### Progressive
Apply progressive enhancement

"In 2016 it's okay to build a website that doesn't work without JavaScript" Hmm.. Is it?

Make sure the UX is already good, **until** JS has loaded and can be improved upon with JS.

### Multithreaded
Web Workers can be used for asynchronous data operations in a separate thread, so you can offload the heavy UI thread to prevent jank. Let the UI thread only update the UI when needed, feed it data from the separate Web Worker thread so that leaves breathing room for complex DOM operations in the UI thread.

## Multi-user WebVR - Martin Splitt
WebVR can be applied in a number of situations:

* Medicine
* Education
* Design
* Architectur
* etc.

The VR world is quite fragmented. GearVR, Vive, Oculus, etc. Some with propietary content.

WebVR brings VR to the browsers, which ofcourse bring cross-platform support!

It can be used with spherical photos, 360˚ video, 3D rendering, or a combination of these techniques.

Using real-time communication with WebRTC, multiple people can be within the same VR environment and interact with it and each other. WebRTC needs a server for a one-time connection and the devices then take over and start communicating directly to each other, without the use of a server in the middle.

THREE.s is a library on top of WebGL to make it simpler to use the WebGL API and create 3D scenes.

Using gradual loading, you can load a 3D world progressively to enable early interaction. When the wireframes are loaded, you are already able to walk in the 3D scene. Then additonal models can be loaded, which are then placed. Low-res environment and model textures can be fetched to make the scene a bit more graphical quite early. Then, as needed, higher resolution textures can be fetched and applied to the 3D scene.

Try to achieve 90-100 frames p/s because our eyes can see more than 60 fps. Higher fps means a higher possible sense of realism.

Combine WebVR with the Gamepad API to be able to use a controller for navigating and interacting with the VR scene.

DOM interaction is not (yet) possible. Buttons in the VR scene need to be hardcoded as boxes that trigger a certain action when interacted with. DOM interaction could be possible in the future so you can use actual `<button>` elements in the VR scene that trigger action in the document or VR world.

The current extremes in the VR markt:

|Google Cardboard|HTC Vive|
|---|---|
|Static position|Position tracking sensors|
|No extra sensors|Loads of sensors built-in|
|No movement|Move around using the positing tracking|
|No use of hands|Controlls which could be used as hands, but no fingers|

Possibilities to achieve exta inputs:

* Leap Motion
* Myo
* Kinect

## Big data, big impact - Lodewijk Nauta

Not quite sure what to make of this. Business cases how they achieved visualising some data interactively and created projects based on that data. But  no real connection with front-end, except that they needed a front-end developer to "improve the charts visuals"...

Visualising Metro occupancy so extra metro carts can be deployed when needed.

Visualising crowdedness in certain areas of a restaurant using WiFI and Bluetooth position tracking.

## Scaling front-end development - Monika Piotrowicz
"What is a front-end developer?"

Front-end developers position themselves on a 'spectrum' between Design and App Development, though most new techniques today gravitate more towards App Development.

A buggy UI is _the_ main reason you will lose trust from your visitors. Build a team and culture around quality and improve skills of people that accomplish this.

### Building a Craft
* Setup language styleguides for HTML CSS and JS
* This helps consistency in code
* Helps new team members get familiar with coding standards
* Form an opinion on why these choices are made

This will help make your code accountable and predictable.

At first, a team might decide on whitespace, then naming conventions, then architecture, etc.

Standardise JS test patterns bases on the language styleguide and choose tools that help your team maintain quality and consistency. E.g. use linting tools for each language, agree on a JS test suite, etc.

Keep developing and evolving your styleguide, embrace new standards and insights. Having a styleguide should make things easier. If something doesn't make it easier or if it's hard to enforce, it might not be worth it to control.

Make sure code reviews happen often where you make members of your team aware of the guide and code quality. Code reviews and comments help creating discussions and learning opportunites for your team. This will build a culture of sharing knowledge and feedback.

Styleguides are useful, people _want_ to write code of high quality.

### Pattern Libraries
* Build a pattern and apply this in certain areas in your application.
* Don't make it a copy-paste library, it wouldn't be maintainable as code might digress from the library.

Create responsive guidelines for:

* Breakpoint defaults
* Grids
* Styling
* Behaviour
* Perf standards
* Tooling
* A11y best practices for inclusiveness

It's important to share expertise with your team, because no one knows _everything_ about front-end development. 

Het is belangrijk om expertise te delen met je hele team, want niemand in je team weet _alles_ van front-end dev. This will lift your team to a higher level.

### UI Library
* Core patterns of the application
* Opinionated for specific use cases that suit _your_ problems, no generic approaches
* Compose a list of variations of several patterns and setup rules when to apply a variation or not
* Which pattern should be standardised?
* Which should be simplified?

Why bother?

* Solve problems once
* More people contributure
* Spend more time on impactful features

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

**Input is exploding**

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

2012: Nothing new

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

jQuery team made Pointer Events Polyfill, PEP.

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
People don't like to wait, be respectful.

Websites are getting bigger, but data is still expensive and latency is high.

Make everybody in your team care about performance.

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

14k rule: serve the most important content in the first 14k.

Above the fold styles should go inline for critical rendering path.

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

Use task runnrs to help automate perf optimisations. Implement in your CI.

Avoid the yo-yo effect. Don't lose weight, then gain weight. Don't optimize perf once and forget about it. Continuously measure perf.

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

## CSP STS PKP SRI ETC OMG WTF BBQ - Scott Helme
- a.k.a. Modern Web Security Standards

### HTTPS
Reasons to migrate to HTTPS:

* HTTP/2 option performance benefits
* Powerful features, geolocation, getUserMedia(), AppCache
* Browsers start to phase out APIs on insecure websites.
* Brotli compression
* SEO boost

Huge incentive to move to HTTPS. Rate of HTTPS adoption is largest in history and still increasing.

Browser support is really good, no need to worry about  older browsers as they ignore the newer security rules and gracefully degrade.

### Security headers
CSP: Content Security Policy

Prevents content injection attacks like XSS.

It's 'just' an HTTP response header, with a number of directives. 

### Mixed Content

Mixed-script.badssl.com to test Mixed Content warnings in your browser.

The green padlock will degrade to neutral UI when mixed content images are loaded.

`block all-mixed-content` directive blocks all mixed content, like images and scripts. Browsers might block mixed content by default.

`upgrade-insecure-requests` directive upgrades requests to insecure resources to HTTPS if available to try load content.

`Content-security-policy-report-only` posts a report to a specified URL so you can monitor mixed content warnings. Sends a JSON report.

### Strict transport security (HSTS)
**Without HSTS**

HTTP requests to HTTPS domains get a 301 redirect to HTTPS. Redirects are slow, 300ms for redirects. SSL can be stripped out by a mitm attack.

**With HSTS**

HSTS solves this issue. It's again a HTTP header.

`Strict-Transport-Security: max-age <nr>`

It overrides user input to enforce HTTPS for secure requests.

### Public Key Pinning
Browers check:

* Name
* Validity period
* Certificate Authority

Malicious CA certs might still not be trusted.

HTTP reponse header:

`public-key-pins: pin-sha256=<hash>; max-age=<seconds>`

Hash of the key in the certificate. When you come back to my website, browsers checks hash in response header with SSL cert to see if it matches.

Certificate leafs at the end on your website, need to go up to the root certificate to guarantee a green padlock. If the chain to the root CA can't be made, it's not a secure cert.

You get a bit more control over who can issue certificates for certain sites.

Also supports a reporting URL:

`Public-Key-Pins-Report-Only: <url>`

### Subresource integrity (SRI)
We trust third parties to serve us the resources we request. There's no guarantee the resource we request even from a secure origin that the response is what we want.

```js
<script crossorigin="anonymous" integrity="sha256-<hash>">
```

The hash does all the work, it checks the hash of the response with the hash specified. If they don't match, the file is not the file that we wanted and the browser blocks it.

### Q&A
The web was built insecure by default, we didn't have HTTPS in the beginning. We're moving to a secure by default era.

Premium SSL certificates are a dated model, it should be enabled by default. Migrating to HTTPS should actually be as simple as a click on a button.

Anywhere you can inject the security headers is a good place. Server config, application level, load balancers, etc.

## Functional animation - Sarah Drasner
Consultant in UX Design and engineering

Staff writer for CSS tricks.

People make a mental map of what's around them.

Wny is this important?

* Websites strat to look the same
* Buttons on a website as CTA
* Growth-hacking
* User-testing

Animation gets a bad rap (rep?).

You draw your eye to a moving thing. When used improperly, it's distracting.

Invisible anim vs immersive anim

invisible = guiding. immersive = drawing attention.

### invisible animation
Connect states to each other.

Transition from one state to another to show users what happened.

Perceived wait time using animation

"If animation feels like sugar on top, that's because you treated it that way."

Users ditch standard loaders on loading pages -> 14 secs wating time.

Good custom loaders increase waiting time to 22 sec.

### spatial awareness
Codrops cinema demo, drag drop demo

### Performance
Opacity and transforms trigger the **least** amount of repaints. Leverage hardware acceleration. Make it a mixing to allow hardware rendering.

Paint flash setting in chrome devtools to let you see repaints.

### DOM/VDOM vs Canvas

DOM Pro's

* Great for UI/UX animation
* Great for SVG that is resolution independent
* Easier to debug

DOM Cons:

* Tanks with a lot of objects
* You have to care about the way you animate

Canvas Pro's

* Dance pixels! Dance!
* Great for 3d work
* Movement of a lot of objects

Canvas Cons

* Harder to make it accessible
* Not resolution independent out of the box. You can make it work for other pixel densities.
* If it breaks, it breaks to nothing.

### SVG
**Very** well supported today. 

* Very crips on anu dosplay.  
* Less http requests
* easily scalable for responsive
small filesize if designed performance.
* Easy to animate
* It has a DOM
* Accessible

What is SVG anim good for?

* Interactive
* Narrative
* UX anim
* Prototypng
* Data vis

SVG animations *can* be really small and performant.

### Greensock
Solves crossbrowser transform origin issues

You can create complex animations without recalculation of timing or keyframes.

GSAP Timeline looks awesome.

GSAP makes svg animation responsive and scalable.

SVG's can be made accessible.

### Narrative

Combine with stories and sound. Really performant, works on mobile. Wow.

Main principle: Design everthing first and slowsly unveil things.

Hold on. Need to pick up my jaw from the floor. These demo's are awesome.

Social coding sites to learn stuff on animation.

Web animation workshops with Val Head.

SVG animation book coming out next year.

## World-wide web, not wealth western web - Bruce Lawson
HTML-coholic :')

Thanks Bruce for the awesome Rick Roll.

Wants to make the web better for..

* Developers
* Consumers
* Business owners
* The next 4 billion people.

Not even half of the world population is on the internet.

Where will your next customers come from? You don't know. 

You can't predict the unpredictable.

There are more people in a large circle in Asia than there are in the rest of the world outside of the circle.

Lots of potential in the Asia region. Massive growth in GDP and mobile connections over the last couple of years.

Out of 690 million internet users in China, 620 go online with a mobile device. And mobile only.

People want to consume the same kinds of information, entertainment, etc. but with huge differences in handsets.

Making the web work on lower-end devices.

Native apps take up space. PWA apps live on the web. Cheaper phones have less storage. Lower-end handsets don't have massive storage amounts.

A 30MB APK takes 30minutes to download over 2G.

Best PWA's come from Asia and Indonesia. Low overhead to install on mobile devices compared to native apps.

Use a manifest in the <head>, it degrades in browsers that don't support it.

No app store, no gate keeper, no update distribution lag, can work offline, linkable.

Data is really expensive in upcoming countries.

Advertising is becoming a parasite that is slowly killing the host. We need to control it as upcoming countries pay big cache.

Opera Mini catches requests to sites. It fetches data over a fast connection and sends it back in one TCP response. It offloads the already overloaded network in the upcoming countries. **Last month** they compressed 29PB of data. CERN alone generates 30PB of data **per year**.

This is why PE is important: Opera Mini does not always exectute all JS on your site. Don't make your site reliant on JS, so you will get the business instead of you competitor who might require JS.

SVG are better than icon fonts <3 Opera Mini doesn't load custom fonts so it doesn't display icon fonts. SVG's are meant to be used for images, so use it.

"It doesn't matter how smart your phone is if your network is dumb".

What can we do?

* PE
* Feature detect
* Compress
* Perf matters
* PWA
* Test opera mini

## Technologic (Human afterall): Accessibility Mix - Leonie Watson
Native browser elements have expected interactions when interacted with.

New a11y API: JS API - Accessibility Object Model

ARIA 1.0 - W3C REC 2014
ARIA 1.1 - W3C WD 2016

Aria roles, attributes, states.

The only assistive technologies that support ARIA are screenreaders.

### Inert elements
You can 'repair' inert elements with a few attributes.

`role="button"`

`aria-expanded="false"`

`aria-controls="content"`

This is badly supported, but it lets the screenreader tell you that the content has changed.

`aria-hidden="true"`

This takes elements out of the a11y tree.

`hidden="hidden"`

Native attributes can be used as well

### Tools
Tenon API: Use it with your build tools. Install a Tenon module for Grunt, Gulp, etc. Send a request API with a key and a url param.

Ember a11y test suite

React a11y test suite

React accessibility API

Angular NGARIA - different, "code tends to be a bit more horrible" :D

Test it yourself, unplug mouse, etc. and use a screenreader.

Generated content will make it into the accessibility tree. Screenreaders read out CSS generated content.

Changing order in flexbox, does not alter keyboard focus sequence. Use tabindex in conjunction with `order: #` to match the visual order.

`aria-flowto="id"` can be used to flow to other elements. But it created a third set of navigation which is only accessible for screenreaders. No support outside of a couple of screenreaders.

Firefox has a "bug" in which it reorders the keyboard sequence when visual order is changed. Could be a solution to keyboard nav issues.

"It doesn't have to be perfect. Just a little bit better than yesterday."

## Joining up the dots - Heydon Pickering

Lots of breakthroughs and innovations have occured in human history. Lots of avoidable wars.

Language is like software for our brain. It can be good and it can be shit.

We like to find patterns in things, as a species. Language is a sum total of all of the consensus over what those patterns are.

The web is an easy and quick way to share your ideas and add it to this living system.

Accessibility does not apply to a very specific demographic. Everyone belongs to a certain minority. There is no average person.

Design as you develop. Work with designers, and develop simultaneously.

We need to get better at debate. 

"Revisist natural language. Learn new language features. When we're joined up, our work is joined up."

