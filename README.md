wavesurfer.js
=============

Interactive navigable audio visualization using
[WebAudio](https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html)
(or [`<audio>` element](http://www.w3.org/wiki/HTML/Elements/audio)
for pre-generated graphics) and
[Canvas](http://www.whatwg.org/specs/web-apps/current-work/multipage/the-canvas-element.html).

Based on [Eiji Kitamura's work](https://github.com/agektmr/AudioStreamer).

With help from [Alex Khokhulin](https://github.com/xoxulin). Thanks!

![Imgur](http://i.imgur.com/vG4FF.png)

API in examples
===============

Create an instance:

    var wavesurfer = Object.create(WaveSurfer);

Initialize it with a canvas element (plus some options):

    wavesurfer.init({
        canvas: document.querySelector('#wave'),
        waveColor: 'violet',
        progressColor: 'purple'
    });

Load an audio file from a URL (via XHR):

    wavesurfer.load('media/sonnet_23.mp3');

You can `playAt(percentage)`, `pause()` and `playPause()`:

    document.addEventListener('keypress', function (e) {
        // spacebar
        if (32 == e.keyCode) {
            wavesurfer.playPause();
        }
    });

There is also a method to visualize drag'n'dropped audio files:

    wavesurfer.bindDragNDrop(targetEl);

HTML5 Audio backend
===================
You can also generate the waveform images on server and use them in combination
with HTML5 Audio, which enjoys wide browser support (as opposed to WebAudio).

See [examples/ex.fm](http://katspaugh.github.com/wavesurfer.js/examples/ex.fm/)
for an API usage example.

License
=======

![cc-by](http://i.creativecommons.org/l/by/3.0/88x31.png)

This work is licensed under a [Creative Commons Attribution 3.0 Unported License](http://creativecommons.org/licenses/by/3.0/deed.en_US).