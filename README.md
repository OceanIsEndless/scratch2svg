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

- [X] Vector costume support
  - [X] ~~Fix positioning bug ([#1](https://github.com/OceanIsEndless/scratch2svg/issues/1))~~
- [ ] Bitmap costume support
- [ ] Various configuration options
  - [ ] Allow exporting without fonts embedded (for use in Scratch)
  - [ ] Allow exporting with or without the default white background
  - [ ] Allow overriding the stage width and height
    - [ ] Automatically detect custom stage bounds from \_twconfig\_ comment
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
    - [ ] [Packaged projects](https://packager.turbowarp.org) (via the [Unpackager](https://turbowarp.github.io/unpackager/))
  - [ ] External websites
    - [ ] Custom URL
    - [ ] [Scratch website](https://scratch.mit.edu)
    - [ ] [Placeholder](https://share.turbowarp.org)
    - [ ] [ScratchBox](https://github.com/ScratchEverywhere/scratchbox)
- [ ] Turn it into a Scratch Addon and/or add a project player to the tool page so that projects can be saved while they're running
  - Useful because a lot of stuff only exists at runtime and isn't saved to the project file such as clones
  - [ ] Implement baseline functionality (generate thumbnail from targets as usual)
    - The difference is, it has to load the data from the Scratch VM instead
  - [ ] Support clones
  - [ ] Support pen layer
    - [ ] Support high quality pen maybe...???!?!
      - It would somehow read or save the pen layer in a vector format. Could be done while the project is running (record changes to the pen layer and then vectorize), or accessed directly through the Scratch VM if such data is saved in the runtime (if the runtime doesn't remember what changes were made then the former option is likely the only way to support this)
      - [ ] Detect \_twconfig\_ comment for hqpen option?
        - Though if supported, high quality pen might just be the default for this tool anyway
  - [ ] Support graphic effects
    - Challenging to vectorize, and may require two different implementations between bitmap/vector costumes depending on how I go about it
    - [ ] Color effect
      - [ ] Black and white when color effect is `Infinity`
    - [ ] Fisheye effect
      - [ ] Backwards
    - [ ] Whirl effect
      - [ ] Backwards
    - [ ] Pixelate effect
    - [ ] Mosaic effect
    - [ ] Brightness effect
    - [ ] Ghost effect (probably the easiest)
  - [ ] Support say/think bubbles
    - Their appearances will have to be recreated in a vector format
    - [ ] Say bubble
    - [ ] Think bubble
  - [ ] Support variable monitors
    - Their appearances will have to be recreated in a vector format
    - [ ] Normal readout
    - [ ] Large readout
    - [ ] List monitor
    - [ ] Slider
- [ ] Go crazy and add an option to embed &lt;script&gt; tags that will make the project functional!!1!... somehow
  - [ ] Embed all assets when enabled (since it will actually be functional)
  - [ ] Port Scratch Everywhere! to... SVG?? 😵‍💫
  - [ ] Make sure everything works OK
    - On a level that is "good enough"
  - This might not actually happen but worth a shot?...
- [ ] 🎉 Maybe make it more modular for use elsewhere or something idk but DONE!

## Credits

The conversion code uses [UZIP](https://github.com/photopea/UZIP.js) to unzip any zipped project files passed as input.

The [Scratch Wiki](https://scratch-wiki.info) was used as reference for some stuff. (E.g. how to read the [Scratch File Format](https://en.scratch-wiki.info/wiki/Scratch_File_Format). <small>I know, I know. Shame on me for not writing the [Scratch spec](https://oceanisendless.github.io/scratch-spec/) already. It's coming soon though! Don't you worry... yet.</small>)
