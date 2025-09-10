# scratch2svg

A buggy tool for generating .svg thumbnails from Scratch projects. Work in progress!!!

## Why?

If you want to take a screenshot of a Scratch project that:

- Is **super high resolution**
- Barely uses your storage
- **Looks good at any size**

Then this is the tool for you!

## Roadmap

Some of these things are probably unnecessary and might not even happen if I find something better to do with my life, but I guess it's good to stay committed. :]

- [X] Vector costume support
- [X] Bitmap costume support
- [ ] Implement various options to meet different needs
  - [ ] Don't embed fonts (for use in Scratch since it already has the fonts)
  - [ ] Transparent background and custom background color
  - [ ] Stage width and height
    - [ ] Detect stage size from \_twconfig\_ comment
  - [ ] Convert known bitmap costumes to vector
    - E.g. assets from the Scratch costume library that were converted to bitmap or are outdated and have a vector version available
    - Possibly disabled by default due to it being inaccurate to the original
  - [ ] Allow embedding metadata into the SVG
    - [ ] Accessibility info (e.g. title, description)
    - [ ] scratch2svg data (e.g. project source, tool config, notes on conversion)
    - [ ] Project  stuff (e.g. target/costume names, creator username, notes)
    - [ ] Full project files ("lossless" scratch2svg conversion)
    - [ ] Custom metadata
      - Whatever the user wants to throw in there I guess?
  - [ ] Provide more configuration options as needed
- [ ] Refine final image
  - [ ] Optimize storage space
    - [ ] Shrink fonts
      - [ ] Choose fonts to use in place of Scratch ones (URL, web safe fonts)
      - [ ] Subset fonts (only include letters that are used by the project)
  - [ ] Make sure it follows SVG semantics
    - [ ] Accessibility things
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
    - [ ] [ScratchBox](https://github.com/ScratchEverywhere/ScratchBox)
  - [ ] Improve upload interface
    - [ ] Allow dragging and dropping files/links anywhere on the page
    - [ ] Make a simple settings window for configuring the final images
    - [ ] Show buttons for interacting with generated SVGs (e.g. download)
- [ ] Allow including variable monitors
  - Their appearances will have to be recreated in a vector format
  - It might also be cool to be able to choose a Scratch version for it to look like and/or have it automatically determine appearance based on the version of Scratch the project was created in
    - [ ] Normal readout
      - [ ] Scratch 3
      - [ ] Scratch 2
      - [ ] Scratch 1
    - [ ] Large readout
      - [ ] Scratch 3
      - [ ] Scratch 2
      - [ ] Scratch 1
    - [ ] List monitor
      - [ ] Scratch 3
      - [ ] Scratch 2
      - [ ] Scratch 1
    - [ ] Slider
      - [ ] Scratch 3
      - [ ] Scratch 2
      - [ ] Scratch 1
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
      - [ ] Scratch 3
      - [ ] Scratch 2
      - [ ] Scratch 1
    - [ ] Think bubble
      - [ ] Scratch 3
      - [ ] Scratch 2
      - [ ] Scratch 1
  - [ ] Support showing/hiding monitors
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
