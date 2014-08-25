Device / Browser Support
========================

A well-cited position of Device and Browser Support


## Position
- [**Mobile First Approach**](http://bradfrostweb.com/blog/web/mobile-first-responsive-web-design/)
  - Semantic HTML and CSS. Content and then presentation.
  - Design and planning for mobile first helps to focus on core content and functionality.
- [**Graded Browser Support**](https://github.com/yui/yui3/wiki/Graded-Browser-Support#three-grades-of-support)
  - Support for Grade-C Browsers (IE6-8) is supported by device detecting for the sole purpose of providing a minimal HTML content only experience without JS, CSS or Polyfils.
  - Support for NO-JS should be limited and should fundamentally provide users with recommendation to seek support for full site experience.
  - Security is #1. Even without JS (client-side validation) the servers application must ensure proper validation is performed. This document's position is only suggesting that the UX experience is limited to something like a [suggestion to enable JS](http://goo.gl/iv8qMc).
- [**Progressive Enhancement**](http://alistapart.com/article/understandingprogressiveenhancement)
  - Minimize usage of Polyfills and Shims where usage should be limited to low impact support for Grade-C browsers.
  - JS support for Grade-C browsers is not recommended.
    - Can negatively impact or limit the experience for the Grade-A browsers. Eg. Many JavaScript libraries do not support IE8 including the newest version of jQuery.
  - Alternate code libs for targeted browsers is also not recommended. Eg. jQuery v1 for <IE9 and jQuery v2 for >IE8. This causes significant fragmentation and significantly more scenarios of failure.


## No JS Support - Additional Cost Examples
- [**Map and GPS**](http://goo.gl/JUp1h1)
  - **Basic Support:** When a user visits a site where the device/browser does not support [Geolocation API](http://dev.w3.org/geo/api/spec-source.html) the user is prompted to manually type in their current location and hit enter to see the map results.
  - **Progressive Enhancement**: When a user visits a site where the device/browser DOES support [Geolocation API](http://dev.w3.org/geo/api/spec-source.html) the site auto locates them, prefills their search field and provides results. (User Approval Prompt Required)
    - This is considered true progressive enhancement support. Notice there are no steps taken to attempt to provide the enhanced features to the browsers that do not support them.
- [**Quick Search**](http://goo.gl/lpWIJy)
  - **WITH JS**: As a user types in a search query into the field, results are dynamically displayed (AJAX), sorted and filtered as they type directly under the field. The backend is responding to the request with properly sorted, filtered results via **JSON**.
  - **W/O JS**: As a user types in a search query into the field, results are  NOT displayed until they click the search button (which is no longer hidden). The backend is responding to the request with properly sorted, filtered results via **HTML** and as part of the "Search Results" page template.
- [**Basic Form**](http://goo.gl/JUp1h1)
  - **WITH JS**: A form is filled out by a user and can dynamically display validation without the need to refresh the screen. Once all validation issues have been corrected, a user can submit the form via an AJAX POST. The same validation rules are preformed on the server and any additional errors will be communicated back via JSON, to be displayed as errors in the form.
  - **WITHOUT JS**: A form is filled out by the user, during which, no feedback/validation is given to the user. Once the form is submitted, the backend will need to re-render the same form page with the appropriate form errors exposed around the form.


## Important Libraries
### **Highly Recommended**
  - [**Monderizr.js**](http://modernizr.com/)
    - Modernizr is a JavaScript library that detects HTML5 and CSS3 features in the user’s browser.
    - Feature Detection vs Device Detection
    - Eg. HTML5 Video (ogg, webm and h264)
  - [**Bootstrap v3**](http://getbootstrap.com/)
    - The most popular HTML, CSS, and JS framework for developing responsive, mobile first projects on the web.
    - Can be used holistically or piecemeal, depending on the application. Eg. Can even be used on sites that will not be RWD.
  - [**Picturefill**](https://github.com/scottjehl/picturefill)
    - A [responsive image](http://picture.responsiveimages.org/) polyfill.
    - very minimal polyfill will full fallback support.
    - There is very limited support for the [<picture>](http://caniuse.com/#search=picture) element currently, however, responsive images are almost a must when designing RWD sites. Using this polyfill is the lesser of two evils when it comes to polyfill use.
  - [**Hammer.js**](http://hammerjs.github.io/)
    - A JavaScript library for multi-touch gestures
    - Allows for simplified event handling for Touch gestures needed for more advanced interactions.

### **Not Needed for Graded Browser Support**
  - [**Respond.js**](https://github.com/scottjehl/Respond)
    - A fast & lightweight polyfill for [CSS3 Media Queries](http://www.w3.org/TR/css3-mediaqueries/)
    - Turning off JS will break Responsiveness
  - [**Selectivizr.js**](http://selectivizr.com/)
    - CSS3 Pseudo-Classes and Attribute Selectors Polyfil
    - turning off JS will break CSS layouts


## Tools
[**caniuse.com**](http://caniuse.com/#compare=ie+8,ie+9,ie+10,chrome+39)
To quickly find what JS and CSS is supported across browsers



