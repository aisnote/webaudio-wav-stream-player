# webaudio-wav-stream-player

instantly play a remote wav stream using [fetch streaming API]() and [WebAudio]()

![npm](https://img.shields.io/npm/v/webaudio-wav-stream-player.svg) ![license](https://img.shields.io/npm/l/webaudio-wav-stream-player.svg) ![github-issues](https://img.shields.io/github/issues/revolunet/webaudio-wav-stream-player.svg)


## Usage

```js
import WavPlayer from 'webaudio-wav-stream-player';

let player = new WavPlayer();
player.play('http//domain/path/to/stream.wav');
player.stop();
```

## FAQ

 - you need CORS on the server streaming .wav
 - or you can proxy the stream with a mitm express server :

```js
// proxy /proxy/http://path/to/stream.wav

app.get('/proxy/*', function (req, res, next) {
  req.pipe(request.get(req.params[0])).pipe(res);
});
```