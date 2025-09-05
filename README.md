# scratch2svg

A buggy tool for generating .svg thumbnails from Scratch projects. Work in progress!!!

## Why?

If you want to take a screenshot of a Scratch project that:

- Is **super high resolution**
- Barely uses your storage
- **Looks good at any size**

Then this is the tool for you!

## Roadmap

Some of these things are probably unnecessary and might not even happen if I find something better to do with my life, but I guess it's good to stay committed. :|

- [ ] Full vector costume support
  - [ ] Fix positioning bug ([#1](https://github.com/OceanIsEndless/scratch2svg/issues/1))
- [ ] Full bitmap costume support
- [ ] Various configuration options
  - [ ] Allow exporting without fonts embedded (for use in Scratch)
  - [ ] Allow exporting with or without the default white background
  - [ ] Provide more configuration options as needed
- [ ] Support loading projects from as many sources as possible ("for fun")
  - [ ] Local files
    - [X] `.sb3` (Scratch 3 project .zip)
      - [X] `.sprite3` (Scratch 3 sprite .zip)
        - [ ] `sprite.json` (Scratch 3 sprite file)
      - [ ] `project.json` (Scratch 3 project file)
    - [ ] `.sb2` (Scratch 2 project .zip)
      - [ ] `.sprite2` (Scratch 2 sprite .zip)
        - [ ] `sprite.json` (Scratch 2 sprite file)
      - [ ] `project.json` (Scratch 2 project file)
      - [ ] Add option to show the saved pen layer
    - [ ] `.sb` (Scratch 1.x project)
      - [ ] `.sprite` (Scratch 1.x sprite)
    - [ ] `.scratch` (Scratch 0.x project)
      - Because why not
  - [ ] External websites
    - [ ] [Scratch website](https://scratch.mit.edu)
    - [ ] [share.turbowarp.org](https://share.turbowarp.org)
    - [ ] [scratchbox](https://github.com/ScratchEverywhere/scratchbox)
    - [ ] Custom URL
- [ ] Go crazy and add an option to embed &lt;script&gt; tags that will make the project functional!!1!... somehow
  - [ ] Embed all assets when enabled (since it will actually be functional)
  - [ ] Port Scratch Everywhere! to... SVG?? 😵‍💫
  - [ ] Make sure everything works OK
    - On a level that is "good enough"

## Credits

The conversion code uses [UZIP](https://github.com/photopea/UZIP.js) to unzip any zipped project files passed as input.

The [Scratch Wiki](https://scratch-wiki.info) was used as reference for some stuff. (E.g. how to read the [Scratch File Format](https://en.scratch-wiki.info/wiki/Scratch_File_Format). <small>I know, I know. Shame on me for not writing the [Scratch spec](https://oceanisendless.github.io/scratch-spec/) already. It's coming soon though! Don't you worry... yet.)
