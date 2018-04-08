## history.scrollRestoration ALSO affets external links

Typically, you want set `history.scrollRestoration` to `manual` to allow custom transitions.

This API applies to the current entry,
which means the scroll state will also NOT be restored when navigating back from external links.

* Demo: http://harttle.github.io/scroll-restoration-demos/history-restoration.html
* Tutorial: https://developers.google.com/web/updates/2015/09/history-api-scroll-restoration
* Spec: https://majido.github.io/scroll-restoration-proposal/history-based-api.html

## scroll restoration happens after `popstate`

This means you can always get current scroll position on popstate,
but not in async callbacks (e.g. Promises).

* Demo: http://harttle.github.io/scroll-restoration-demos/history-restoration-timing.html
