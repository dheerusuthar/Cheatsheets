# Web APIs

## HTTP

Fetch: https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch

  ```js
  fetch('./api/some.json')
    .then(
      function(response) {
        if (response.status !== 200) {
          console.log('Looks like there was a problem. Status Code: ' +
            response.status);
          return;
        }

        // Examine the text in the response
        response.json().then(function(data) {
          console.log(data);
        });
      }
    )
    .catch(function(err) {
      console.log('Fetch Error :-S', err);
    });
  ```

XMLHttpRequest:

  ```js
  // JSON
  var req = new XMLHttpRequest();
  req.responseType = 'json';
  req.open('GET', url, true);
  req.onload  = function() {
    var jsonResponse = req.response;
    // do something with jsonResponse
  };
  req.send(null);


  // JSON
  function reqListener() {
    var data = JSON.parse(this.responseText);
    console.log(data);
  }
  function reqError(err) {
    console.log('Fetch Error :-S', err);
  }
  var oReq = new XMLHttpRequest();
  oReq.onload = reqListener;
  oReq.onerror = reqError;
  oReq.open('get', './api/some.json', true);
  oReq.send();
  ```



## Web Workers
- background thread (other than UI thread)
- cannot access DOM
- different context window

## Sevice Worker
- Proxy between browser and network. Handles network requests. Thus enabling offline experience.
- it's web worker and more
- cannot access DOM

## Web Socket
Communicate from browser to server.

- Socket.IO: A long polling/WebSocket based third party transfer protocol for Node.js.
