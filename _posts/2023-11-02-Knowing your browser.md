## Understanding Web Browsers & Browser Engines

A **web browser** is a software application designed to access information on the Internet, displaying web pages, images, and videos identified by Uniform Resource Locators (URLs). These browsers retrieve resources from web servers and present them on a user's device.

When selecting a web browser, one is essentially choosing both a **browser engine** and a **rendering engine**. These terms are sometimes used interchangeably. But what exactly is a browser engine?

### Browser Engine: Decoding Web Pages

A *browser engine* is a core component of major web browsers, responsible for transforming HTML documents and other resources into an interactive visual representation on a user's device. It calculates graphical coordinates based on CSS rules, translating raw code into the visible content users see on screen. This engine ensures the layout, page content, and styling specified in a web page's code are accurately displayed.

The *browser engine*, along with the *rendering engine* and *JavaScript engine*, collaborates to convert raw web code into a viewable and usable format within a browser. These engines work together to interpret web developer instructions and render them visually.

### Various Browser Engines

Multiple browser engines exist due to the open standards of the Web platform:

- **Gecko:** Developed by Mozilla, it powers Firefox, Thunderbird, and the Pale Moon browser `etc..`
- **Blink:** Used by all Chromium-based browsers, including Chrome, and applications built with [CEF](https://en.wikipedia.org/wiki/Chromium_Embedded_Framework), Electron, or frameworks embedding Chromium.
- **WebKit:** Created by Apple for Safari, it was forked from the KDE project's KHTML engine. Google initially used WebKit for Chrome but later forked it to create the Blink engine.
- **Trident and EdgeHTML:** Previously proprietary to Microsoft, these engines powered Internet Explorer and Edge browsers. Microsoft now uses Blink for its Edge browser.
- **Servo:** An experimental browser engine developed by Mozilla Research, designed to exploit Rust's memory safety properties and concurrency features.

### How Browser Engines Work ?

A browser engine acts as a translator, converting raw web code into a formatted page comprising text and graphics. It interprets web developer instructions, determining how code impacts on-screen elements. The engine is crucial in ensuring web pages appear differently across various browsers due to differences in browser engines. Additionally, it needs to support `new standards` as the Internet evolves.

When a browser loads a website, it requests data from a server, which is sent back in HTML format, describing the page's structure. Browser engines include parsers converting data formats, creating the in-memory Document Object Model (DOM). The layout engine calculates sizes and positions of elements based on styles, generating the visual page. Finally, the browser engine paints the page, creating the visible, interactive web experience for users.

### Blink Ecosystem & Google Monopoly !

Google's **search engine**, a powerful tool for navigating the vast internet, helps users find relevant information easily with the algorithm, With that being said having most of the browsers under blink might give an upperhand for google [I know this may sound like a controversy] [Web Integrity Api](https://news.ycombinator.com/item?id=36854114) was an example of google changing the standard web.[(depriciated)](https://en.wikipedia.org/wiki/Web_Environment_Integrity)with that being said waiting for Servo engine it is said to have a comeback , yet google having the upperhand in implementing web-standards is a pain that will never be resolved soon. 