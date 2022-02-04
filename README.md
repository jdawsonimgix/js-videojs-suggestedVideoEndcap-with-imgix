# imgix HLS functionality combined with videojs-suggestedvideoendcap!

This JavaScript demo shows how you can get HLS video using imgix while also controlling the ads at the end of your videos with the videojs-suggestedVideoEndcap plugin.

[Click here to see the demo in action.](https://inspiring-poincare-56d20b.netlify.app/)

## Steps to follow:

1. Go to the [npm install page](https://www.npmjs.com/package/videojs-suggestedvideoendcap/v/1.2.0) and follow the install instructions for the videojs-suggestedVideoEndcap plugin. You can also see how the code is structured by going to the `index.html` file.

2. When calling the `<video>` source, make sure to set `type` to `"application/x-mpegURL"`

```
<video
    id="my-video"
    class="video-js"
    controls
    preload="auto"
    width="640"
    height="264"
    data-setup="{}"
>
<source  src="https://tom.imgix.video/gotopening.mp4?fm=hls"
type="application/x-mpegURL">
</video>
```
