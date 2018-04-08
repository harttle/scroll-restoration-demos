## history.scrollRestoration

Typically, you want set `history.scrollRestoration` to `manual` to allow custom transitions.

This API applies to the current entry,
which means the scroll state will also NOT be restored when navigating back from external links.

* Demo: http://harttle.github.io/navigation-bugs/history-restoration.html
* Tutorial: https://developers.google.com/web/updates/2015/09/history-api-scroll-restoration
* Spec: https://majido.github.io/scroll-restoration-proposal/history-based-api.html
