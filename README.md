# Retimer

Another Retimer tool but this one can pull up the YouTube video and get the data from there.

## How to use

1. Go to [the hosted site](https://ewanlyon.github.io/retimer/).
   - Or download the index.html file and serve it via Node like `npx serve .` or Python via `python -m http.server`. You cannot run it just from opening it because of YouTube's embedding.
2. Paste in the YouTube URL or the YouTube video id into the top box.
3. Find the start frame of the speedrun. Use the frame navigation buttons at the bottom to get it perfect.
4. Hit "Set Start"
5. Navigate to the end of the run.
6. Hit "Set End"
7. Select the FPS of the game (if it is a locked framerate) or video
8. Copy the time by clicking on it.

## Caveats

Seeking frames could be off by a frame every now and then. YouTube's iframe API does NOT allow seeking by individual frames or exposes the keybindings (`,` and `.`) to do so. The way frames are advanced or returned is by getting the current time of the video and adding 16.67ms (1 / 60) to it. This should work in theory but I cannot guarantee timing down to the exact frame meaning that your time might be off by 2 frames (33ms). If this is an issue (it really isn't unless you are a top runner of SMB1), then please open the video in video editing software and check manually which you were probably already doing.

## Development Rationale

### Why?

I saw a video on the current methods to retime and it involved too many steps or downloading stuff.

### Why a single HTML file?

I wanted to keep it as small, simple and lightweight as possible. Even separate CSS and JS files felt a bit overkill (though if you are learning to program, please for the love of god separate it out, I am unfortunately a "professional"). I could've easily turned this into some goliath React codebase when it literally just needs to do some basic arithmetic.
