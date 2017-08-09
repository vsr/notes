# Error logging


## Code snippet for logging client side errors to a server or Google Analytics

```js
window.addEventListener('error', function(e) {
   var errorText = [
       'Message: ' + e.message,
       'URL: ' + e.name,
       'Line: ' + e.lineno,
       'Column: ' + e.colno,
       'Stack: ' + (e.error && e.error.stack || '(no stack trace)')
   ].join('\n');

   // Example: log errors as visual output into the host page.
   // Note: you probably don’t want to show such errors to users, or
   //       have the errors get indexed by Googlebot; however, it may
   //       be a useful feature while actively debugging the page.
   var log = document.createElement('pre');
   log.style.position = 'fixed';
   log.textContent = errorText;
   document.body.appendChild(log);

   // Example: log the error to remote service.
   // Note: you can log errors to a remote service, to understand
   //       and monitor the types of errors encountered by regular users,
   //       Googlebot, and other crawlers.
   var client = new XMLHttpRequest();
   client.open('POST', 'https://example.com/logError');
   client.setRequestHeader('Content-Type', 'text/plain;charset=UTF-8');
   client.send(errorText);

   // Example: log the error to Google Analytics
   // Note: same as above, but assumes that you’ve loaded ga.js already
   //       and want to log the error as a Google Analytics event.
   ga('send', 'event', {
       eventCategory: 'Error',
       eventAction: e.name || '(no error name)',
       eventLabel: errorText,
       nonInteraction: true
   });
});
```

[Source](https://developers.google.com/search/docs/guides/debug-rendering)
