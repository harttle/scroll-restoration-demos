## history.scrollRestoration ALSO Affets External Links

Typically, you want set `history.scrollRestoration` to `manual` to allow custom transitions.

This API applies to the current entry,
which means the scroll state will also NOT be restored when navigating back from external links.

* Demo: http://harttle.github.io/scroll-restoration-demos/history-restoration.html
* Tutorial: https://developers.google.com/web/updates/2015/09/history-api-scroll-restoration
* Spec: https://majido.github.io/scroll-restoration-proposal/history-based-api.html

## Scroll Restoration Happens AFTER `popstate`

This means you can always get current scroll position on popstate,
but probably not in async callbacks (e.g. Promises).
The actual restoration timing is implementation-related:
It takes one [animation frame][requestAnimationFrame] in Chrome, and several more in Safari.

* Demo: http://harttle.github.io/scroll-restoration-demos/history-restoration-timing.html

## Get Scroll Position

To get scroll position, there's many APIs with different compatibility issues such as:

* `window.scrollY`
* `window.pageYOffset`
* `document.body.scrollTop`
* `document.documentElement.scrollTop`
* `document.scrollingElement.scrollTop`

Here we don't examine these APIs one by one, here's a demo to test with:

* Demo: http://harttle.github.io/scroll-restoration-demos/scroll-apis.html
* Tutorial: https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollY

## NEVER Set scrollY or pageYOffset

Always use `scrollTo` to scroll your page.
Through `scrollY` and `pageYOffset` are NOT readonly, which means they can be set,
they WON'T change anymore once assigned. Take care!

* Tutorial: https://developer.mozilla.org/en-US/docs/Web/API/Window/scroll

## scroll event not fired on UIWebview

Typically `scroll` event will be fired on scroll restoration. 
Whereas for iOS UIWebview-based browsers no `scroll` event will be fired.
Try UC browser, Baidubox browser.

* Demo: http://harttle.github.io/scroll-restoration-demos/scroll-event.html

[requestAnimationFrame]: https://developer.mozilla.org/en-US/docs/Web/API/window/requestAnimationFrame
