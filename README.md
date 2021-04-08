# noteit-app
Both front and back end hosted on heroku.
## Upgrade http to https
HTTP requests are upgraded(Actually redirected) to HTTPS by adding the below code to the script tags in index.html of react app.

```html
    <script>
      const isRunningOnLocalhost = Boolean
      (
        window.location.hostname === 'localhost' ||
        // [::1] is the IPv6 localhost address.
        window.location.hostname === '[::1]' ||
        // 127.0.0.0/8 are considered localhost for IPv4.
        window.location.hostname.match(
          /^127(?:\.(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)){3}$/
          )
      );
      if ( !(isRunningOnLocalhost) && location.protocol !== 'https:' )
      {
        location.replace(`https:${location.href.substring(location.protocol.length)}`);
      }
    </script>

```
