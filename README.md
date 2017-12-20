# embed-miner
A miner you can embed in an IFRAME.

`miner.html` uses `leat-stratum-proxy.js` on the back end and pulls `leat-mine.js` from the server to the client.

For it to work on your own server you serve the leat-mine.js file and run the leat-stratum-proxy.js file somewhere.

# Usage

The following will work as is (however it will use my servers unless you serve the files).

```html
<html>
  <head>
    <title>I-Frame Example</title>
  </head>
  <body>
    <h1> leat.io embedded miner: </h1>
    <script src="https://leat.io/lib/leat-mine.js"></script>
    <iframe src="https://leat.io/miner.html?u=leathan" style="width: 400px; height: 300px; border: none"></iframe>
    <!-- <iframe src="https://leat.io/miner.html?a=YOUR_MONERO_ADDRESS"></iframe> -->
  </body>
</html>
```
