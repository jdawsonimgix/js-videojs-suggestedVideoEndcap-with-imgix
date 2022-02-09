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

3. You can then replace the `url` and `imgix` parameters what the ads you want to add at the end of your videos.

Note: It is recommended you limit the number of ads to 3.

```
<script src="videojs.suggestedVideoEndcap.js" type="text/javascript"></script>
<script>
  'use strict';

  var video = videojs('my-video');
  video.suggestedVideoEndcap({
    header: 'You may also like',
    suggestions: [
      {
        title: 'Suggested article One',
        url: 'https://www.google.com/search?q=cats',
        image: 'https://jdawson.imgix.net/vapor-cat-1.jpeg', // could be an animated GIF
        alt: 'Description of photo', // optional photo description, defaults to the title
        target: '_blank' // can be any anchor target type
      },
      {
        title: 'Suggested Article One',
        url: 'https://www.google.com/search?q=dogs',
        image: 'https://jdawson.imgix.net/istockphoto-1280623255-1024x1024.jpeg',
        target: '_self' // defaults to self if no target value is present
      }
    ]
  });
```
