# ruffle-demo

<<<<<<< HEAD
ruffle-demo is an example of how to include Ruffle in your website.
It also serves as a nice local test to run Ruffle in the web locally, for developers.

## Using ruffle-demo

### Hosted demo

To view this demo online right now, [check out the hosted demo](https://ruffle.rs/demo).

It's exactly the same code as this directory, updated nightly.

### Run your own demo

After [building ruffle-web](https://github.com/ruffle-rs/ruffle/blob/master/web/README.md#building-from-source),
you can run `npm run demo` in the `web` folder to launch the demo.

It will start a local web server and print the address in the console.
Navigate to that website (usually [http://localhost:8080](http://localhost:8080)) in your browser.

### Configuring the demo

The demo provides the ability to have a list of sample SWFs to choose from.
This can be helpful if you have a list of useful SWFs to test through, and we use it ourselves
to showcase Ruffle on various games or animations.

To use this, add a new file `swfs.json` in this directory. The contents should look like this:

```json
{
  "swfs": [
    {
      "location": "logo-anim.swf",
      "title": "Ruffle Logo",
      "author": "Ruffle contributors",
      "authorLink": "https://ruffle.rs",
      "config": {
        "autoplay": "on",
        "backgroundColor": "#31497D",
        "letterbox": "off",
        "unmuteOverlay": "hidden"
      }
    },
    {
      "location": "swfs/bitey1.swf",
      "title": "Bitey of Brackenwood",
      "author": "Adam Phillips",
      "authorLink": "https://bitey.com",
      "type": "Animation"
    },
    {
      "location": "swfs/saturday_morning_watchmen.swf",
      "title": "Saturday Morning Watchmen",
      "author": "Harry Partridge",
      "authorLink": "https://twitter.com/HappyHarryToons",
      "type": "Animation"
    },
    {
      "location": "swfs/synj1.swf",
      "title": "Synj vs. Horrid Part 1",
      "author": "Dan Paladin",
      "authorLink": "https://www.thebehemoth.com",
      "type": "Animation"
    },
    {
      "location": "swfs/synj2.swf",
      "title": "Synj vs. Horrid Part 2",
      "author": "Dan Paladin",
      "authorLink": "https://www.thebehemoth.com",
      "type": "Animation"
    },

    {
      "location": "swfs/alien_hominid.swf",
      "title": "Alien Hominid",
      "author": "Tom Fulp and Dan Paladin",
      "authorLink": "https://www.newgrounds.com",
      "type": "Game"
    },
    {
      "location": "swfs/flyguy.swf",
      "title": "FlyGuy",
      "author": "Trevor van Meter",
      "authorLink": "https://www.heytvm.com",
      "type": "Game"
    },
    {
      "location": "swfs/marvin_spectrum.swf",
      "title": "Marvin Spectrum",
      "author": "Bryan Singh",
      "authorLink": "https://www.hotbryan.com",
      "type": "Game"
    },
    {
      "location": "swfs/wasted_sky.swf",
      "title": "Wasted Sky",
      "author": "Tom Fulp",
      "authorLink": "https://www.newgrounds.com",
      "type": "Game"
    }
  ]
}
```

## Building, testing or contributing

Please see [the ruffle-web README](https://github.com/ruffle-rs/ruffle/blob/master/web/README.md).

=======
ruffle-selfhosted is the intended way to get Ruffle onto your website.

You may either include it and forget about it, and we will polyfill existing Flash content,
or use our APIs for custom configurations or more advanced usages of the Ruffle player.

## Using ruffle-selfhosted

For more examples and in-depth documentation on how to use Ruffle on your website, please
[check out our wiki](https://github.com/ruffle-rs/ruffle/wiki/Using-Ruffle#web).

### Host Ruffle

The `selfhosted` package is configured for websites that do not use bundlers or npm and just want
to get up and running. If you'd prefer to use Ruffle through npm and a bundler, please 
[refer to ruffle core](https://github.com/ruffle-rs/ruffle/tree/master/web/packages/core).

Before you can get started with using Ruffle on your website, you must host its files yourself.
Either take the [latest build](https://github.com/ruffle-rs/ruffle/releases)
or [build it yourself](https://github.com/ruffle-rs/ruffle/blob/master/web/README.md), and make these files accessible by your web server.

Please note that the `.wasm` file must be served properly, and some web servers may not do that
correctly out of the box. Please see [our wiki](https://github.com/ruffle-rs/ruffle/wiki/Using-Ruffle#configure-wasm-mime-type)
for instructions on how to configure this, if you encounter a `Incorrect response MIME type` error.

### "Plug and Play"

If you have an existing website with flash content, you can simply include Ruffle as a script and
our polyfill magic will replace everything for you. No fuss, no mess.

```html
<script src="path/to/ruffle/ruffle.js"></script>
```

### Javascript API

If you want to control the Ruffle player, you may use our Javascript API.

```html
<script>
    window.RufflePlayer = window.RufflePlayer || {};

    window.addEventListener("DOMContentLoaded", () => {
        let ruffle = window.RufflePlayer.newest();
        let player = ruffle.createPlayer();
        let container = document.getElementById("container");
        container.appendChild(player);
        player.load("movie.swf");
    });
</script>
<script src="path/to/ruffle/ruffle.js"></script>
```

## Building, testing or contributing

Please see [the ruffle-web README](https://github.com/ruffle-rs/ruffle/blob/master/web/README.md).