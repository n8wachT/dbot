## imgur

Various imgur functionality.

### Description

Posts information on imgur links which are pasted into the channel and provides
functionality to generate a random imgur link.

### Config

#### imagelength: 5
Length of slugs generated by the random imgur functionality.

#### nsfwwarn: true
Warn that images generated by the ~ri command may be NSFW.

#### apikey
Key to use with the imgur API.

#### highscore: ricount
Quote category to use for a 'highscore;' used to run games with the web
/random page, by storing a highscore based on some arbitrary rule in the
chosen quote category (say, how far can you get before seeing a turtle). Then,
on the imgur random page you can press 'c' to see a countdown towards the last
stored value in the highscore quote category. If you beat the highscore, simply
add the winning score to the quote category.

### Commands

#### ~ri
Generate a random imgur image and post a link to it in the channel.

### API

#### getRandomImage(callback)
Generate a random imgur image by generating random slugs and then testing for
their existence until it finds one which exists (and hasn't been deleted).
Callback is given with two parameters, the URL of the generated image, and the
slug for the generated image.

#### getImageInfoString(slug, callback)
Return a string containing info about the image with the given slug from the
imgur API. Callback is called with one argument, the info string.

#### getImageInfo(slug, callback)
Return data from the imgur API on an image with the given slug. Callback is
called with one argument, the information returned by the API.

### Web

#### /imgur/random

A web page which loads a random image from imgur. You can press the space bar to
load a new image, and information about the images are shown on the top-left of
the page. You can press 'c' to view a highscore count (as documented above).

#### /imgur/stats

Show statistics on the total use of the imgur module. 

### Hooks

#### link
Posts information about an imgur link when one is linked in the channel.
