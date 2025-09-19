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
- [ ] Add configuration options
  - [ ] Don't embed fonts (for use in Scratch since it already has the fonts)
    - Fonts are currently causing a lot of storage bloat, so add some storage saving options as well:
      - [ ] Convert &lt;text&gt; elements to &lt;path&gt; elements
        - Will need to find a good tool or library to do this
        - Might store paths ahead of time or convert text elements directly depending on implementation
      - [ ] Keep &lt;text&gt; elements but only include used characters
        - E.g. if the text in a project only says "Hello!", then encode just the info needed to render "H," "e," "l," "o," and "!" in the embedded font file
        - Probably need a good libarary for this
      - Keep &lt;text&gt; elements but choose different font(s)
        - Saves space but less accurate visually
  - [ ] Transparent background and custom background color
  - [ ] Stage width and height
    - [ ] Make UI adapt to different stage sizes
    - [ ] Detect stage size from \_twconfig\_ comment
  - [ ] Convert known bitmap costumes to vector
    - E.g. assets from the Scratch costume library that were converted to bitmap or are outdated and have a vector version available
    - Possibly disabled by default due to it being inaccurate to the original
  - [ ] Allow embedding metadata into the SVG
    - [ ] Accessibility info (e.g. title, description)
    - [ ] scratch2svg data (e.g. project source, tool config, conversion date)
    - [ ] Project  stuff (e.g. target/costume names, creator username, notes)
    - [ ] Full project files ("lossless" scratch2svg conversion)
      - [ ] Losslessly compress it somehow to save space
    - [ ] Custom metadata
      - Whatever the user wants to throw in there I guess
      - [ ] Allow setting title/description manually
  - [ ] Provide more configuration options as needed
- [ ] Refine final image
  - [ ] Optimize storage space (only encode exactly what is necessary)
  - [ ] Make sure it follows SVG semantics
    - [ ] Include all necessary attributes, elements, fallbacks?, etc
    - [ ] Bring outdated stuff like xlink up-to-date to make it futureproof
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
      - This would probably be nicer than hoping the user is able to right-click &gt; "Save Image As..."
- [ ] Allow including variable monitors
  - Their appearances will have to be recreated in a vector format
    - [ ] Normal readout
    - [ ] Large readout
    - [ ] List monitor
    - [ ] Slider
  - [ ] Make sure it's the right color
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
    - [ ] Color effect (idk if easy)
      - [ ] Black and white when color effect is `Infinity`
    - [ ] Fisheye effect (could be impossible)
      - [ ] Backwards
    - [ ] Whirl effect (maybe impossible)
      - [ ] Backwards
    - [ ] Pixelate effect (I have no idea what this entails)
    - [ ] Mosaic effect (probably slightly easy)
    - [ ] Brightness effect (second easiest)
    - [ ] Ghost effect (the easiest)
  - [ ] Support say/think bubbles
    - Their appearances will have to be recreated in a vector format
    - [ ] Say bubble
    - [ ] Think bubble
  - [ ] Suport ask and wait box
- [ ] Support making it look like different Scratch versions
  - [ ] Scratch 2
    - [ ] Variable monitors
    - [ ] Graphic effects
    - [ ] Say/think bubbles
    - [ ] Any other minor inconsistencies
  - [ ] Scratch 1
    - [ ] Variable monitors
    - [ ] Graphic effects
    - [ ] Say/think bubbles
    - [ ] Any other minor inconsistencies
  - [ ] Scratch 0
    - [ ] If there's anything different on this front then... um... recreate it!
  - [ ] &lt;insert anything else here&gt;
    - [ ] High contrast make variable monitors look different?
    - [ ] Mods of Scratch change the accent color (variable monitors, ask and wait box)?
  - If I miraculously manage to do both this AND make the project functional, I would likely have attained perfection and created a universal runtime which supports all versions of Scratch, thus making running the Scratch 2 and Scratch 1 projects and any other projects possible. Though it would be at this point that I should probably reconsider my life choices
- [ ] Go crazy and add an option to embed &lt;script&gt; tags that will make the project functional!!1!... somehow
  - [ ] Embed all assets when enabled (since it will actually be functional)
  - [ ] Port Scratch Everywhere! to... SVG?? 😵‍💫
  - Joking, not going to fork Scratch Everywhere!, though I may reference it?
    - When the WASM port happens, could maybe use that if it works for this magically idk anymore
    - [ ] Support updating monitors, applying graphic effects to sprites, etc (expose relevant functions needed for rendering at runtime)
      - Anything that was preprocessed must be overhauled
    - [ ] Make runtime work (at this point I'm either cooking or cooked)
  - [ ] Make sure everything works OK
    - On a level that is "good enough"
  - This might not actually happen but worth a shot?...
- [ ] 🎉 Maybe make it more modular for use elsewhere or something idk but DONE!

As you can see I am overly ambitious, and it is probably the death of any real project I hope to complete. Baby steps I guess. :&gt;

## Credits

The conversion code uses [UZIP](https://github.com/photopea/UZIP.js) to unzip any zipped project files passed as input.

The [Scratch Wiki](https://scratch-wiki.info) was used as reference for some stuff. (E.g. how to read the [Scratch File Format](https://en.scratch-wiki.info/wiki/Scratch_File_Format). <small>I know, I know. Shame on me for not writing the [Scratch spec](https://oceanisendless.github.io/scratch-spec/) already. It's coming soon though! Don't you worry... yet.</small>)
