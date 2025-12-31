# YouTube uBlock Origin Filters

This is a collection of custom [uBlock Origin](http://github.com/gorhill/uBlock) (uBO) filters for YouTube that I've built up over the past few years. In response to YouTube's decision to use AI age verification (which started August 13, 2025 in the US) to guess if you're over 18 (which definitely won't go wrong and ask for your ID to fix it), I've decided to release these filters to the public, and commit to minimising my usage of YouTube as much as possible.

As a bonus, I've also included some extensions and userscripts I use for YouTube as well.

This filter list was originally hosted as a GitHub Gist. Since then, it has gained support for YouTube's new 2025 player UI (this added 20 new rules alone), and fixed a bunch of broken rules, possibly due to the 2025 UI update.

## Warnings

- I would highly recommend looking through my filter list to see the changes it will make before actually using them.
  - If you don't want all the changes, you can copy and paste the filters into uBO's custom filter list (under "My filters"), and comment or delete ones you don't want. My filters will be split into multiple files in the future.
- These filters will (assuming they haven't broken):
  - Unround video thumbnails.
  - Hide many monetisation features (the "Thanks" button, "Join" button for memberships, and members-only videos to name a few).
  - Hide YouTube Shorts from recommendations.
  - Convert the home page to just a grid of videos, and make more fit on one screen.
  - The default setting of 5 videos per row will likely be too small for an 11 or 13 inch laptop, and can be adjusted by searching
    for `--ytd-rich-grid-items-per-row` (paste it into the search box on the "My filters" screen), and adjusting the value to 4 (or even 3)
    videos per row. I unfortunately do not know how to make it dynamically adjust based on viewport size at this time.
- These filters may not work for you, due to YouTube's many A/B tests and constant UI updates.
- I may update these filters periodically if I find issues. Don't expect this too often, though.
  - Feel free to post fixes yourself.
- Your browser must support the [`:is()`](https://www.w3schools.com/cssref/sel_is.php) CSS pseudo-class to use many of these filters,
  supported since Firefox v78 (released in July 2020). Support for the [`:has()`](https://www.w3schools.com/cssref/sel_has.php) pseudo-class
  is also recommended, otherwise uBlock will fall back to a slower implementation.
- my filter comments may contain swears if that bothers you
  - you don't want to know what they were like before editing them to upload here; you're getting the abridged version

## How to use these filters

1.  Install [uBlock Origin](https://github.com/gorhill/uBlock) (or another ABP-compatible ad blocker), if you haven't already for some reason.
    - If you're on Chrome (or another Chromium-based browser, e.g. Edge), install [LibreWolf](https://librewolf.net/installation/) or [Firefox](https://www.firefox.com/), then install uBlock Origin using the link above.
    - These filters haven't been tested on [uBlock Origin Lite](https://github.com/uBlockOrigin/uBOL-home) (does it even support these custom filters?)
2.  Open uBO's settings (click on the extension icon, then the "gears" icon), and go to the "Filter lists" tab.
3.  Expand the "Import..." section, and paste [this link](https://codeberg.org/Sparronator9999/yt-ublock-filters/raw/branch/main/yt-filters.txt) into the box that appears.
4.  Click "Apply changes" and wait for the filter list to update.
5.  ???
6.  Profit!

## Bonus: other extensions I use

- [SponsorBlock](https://sponsor.ajay.app/): skip YouTube sponsors (and more) using crowd-sourced timestamps.
  - [Odysee Sponsor Skipper](https://github.com/furdiburd/sponsorblock-odysee-firefox) can be used to skip sponsors on YouTube videos that are automatically synced to Odysee.
- [DeArrow](https://dearrow.ajay.app/): Replace clickbait with more descriptive titles. Also crowd-sourced.
  - This extension requires a one-time donation to start using straight away.
    You can also request a free license key through the extension, which will be granted after 24 hours.
- [Return YouTube Dislike](https://returnyoutubedislike.com/): self-explanatory.
- [SoundFixer](https://github.com/valpackett/soundfixer): I use it to convert videos to mono when people
  use the stereo recording feature on their iPhones (which is most iPhone recordings these days...)
  - This extension is compatible with *most* sites that show video, with the only exception being those that show cross-domain media.
- [Video Speed Controller](https://github.com/codebicycle/videospeed): Okay, I know YouTube has this built-in, but this allows me to
  precisely dial in the video speed on other websites to fix people not talking quick enough lol
- [Enhancer for YouTube](https://www.mrfdev.com/enhancer-for-youtube): Currently in a **buggy state**, likely due to YouTube's constant UI updates. I still use it to:
  - force 1080p and H.264 encoding
  - hide end screens when they show over actual content at the end of a video
  - expand the video player to take up more of the screen than in the built-in "cinema mode"
  - prevent video autoplay (because Firefox can't stop it for some reason, even when set to "block audio and video"...)
- [Violentmonkey](https://violentmonkey.github.io/) with the following userscripts (some of which I've been using for more than a year at this point):
  - [Youtube - No scroll to top on timestamps](https://greasyfork.org/en/scripts/438943-youtube-no-scroll-to-top-on-timestamps): When using Enhancer for YouTube or Firefox's built-in Picture-in-picture mode, this is useful when skipping chapters using a random commenter's timestamps.
  - [YouTube Usability](https://greasyfork.org/en/scripts/491283-youtube-usability): Disables the Home, End, and 0-9 number key shortcuts, which I frequently mistype, which causes YouTube to skip to a random point in the video.
  - [YouTube link redirect remover](https://greasyfork.org/en/scripts/424936-youtube-link-redirect-remover): Removes tracking from external URLs in video descriptions.
  - [YouTube Automix Remover](https://greasyfork.org/en/scripts/539118-youtube-automix-remover): Removes newly-added "Automix" playlists, appearing when you click on ANY YouTube video (even non-playlist videos...)
  - [YouTube CPU-Tamer Upgrade](https://greasyfork.org/en/scripts/495119-youtube-cpu-tamer-upgrade): Optimises YouTube for use on older devices. Not sure if this one is still necessary.
  - I also used to use [Simple YouTube Age Restriction Bypass](https://github.com/zerodytrash/Simple-YouTube-Age-Restriction-Bypass/), but that broke about a year ago.
