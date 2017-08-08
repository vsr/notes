# Service Worker


## Basics reference

* [MDN](https://developer.mozilla.org/en/docs/Web/API/Service_Worker_API)

* [Google Web Fundamentals](https://developers.google.com/web/fundamentals/getting-started/primers/service-workers)

* [Status](https://jakearchibald.github.io/isserviceworkerready/)



## Gotcha

### Service Worker does not update even after reloading.

The service worker JS file must not be cached from the server side. Set the max-age cache header to 0.

* [Reference tweet](https://twitter.com/steveworkman/status/882957222120235008)
* The SW spec is being updated ([here](https://github.com/w3c/ServiceWorker/issues/893) and [here](https://github.com/w3c/ServiceWorker/issues/1104))to avoid caching of SW JS file.
* Status on [Firefox](https://bugzilla.mozilla.org/show_bug.cgi?id=1290944#c65) and [Chrome](https://bugs.chromium.org/p/chromium/issues/detail?id=675540).
