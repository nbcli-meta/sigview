# sigview
Real-Time Signal Visualization Research

[![DOI](https://zenodo.org/badge/354954050.svg)](https://doi.org/10.5281/zenodo.16340297)


---

### sigv.js (current)

Removing all engines tested for Gibberwocky and gl.commandline languages, and opted for using native Max and Javascript. Added textfield object to enter commands, with an added Max js object referencing sigv.js where coding can occurr as well as the textfield.  Compiling of sigv.js happens on save, for example when using Atom as IDE.  ```js open``` entered into the textfield launches sigv.js in Atom.

At this stage of the research, Orca remains the preferred sequencer, and as such, the OSC module has been activated to communicate with Orca via port 7777.  ```sigx``` and ```sigy``` have a new subroute ```div``` to specify a divisor (default set to 0.1).  Orca sends values 0 thru 36, so ```div``` can be used to amend this scale.



### sigv-gl

*Updated:* removed clifford attractor due to a code conflict, added default start code:

```js
// initialize SIGV messageboard
s = message('sigv')

// set camera position
s.cam.position('0 0 4') // peak signal specs will be seen

// Lorenz Attractor
l = s.lorenz
l.sample() // sample initial parameters and display
l.activate(1) // activate lorenz attractor by connecting [wrld], begins cycle metro

// Attractor mesh
m = l.mesh
m.scale(0.5)
m.rotatexyz('0 0 -57')
m.draw_mode('points')
m.point_size.seq([.25,1,.5,.75],Euclid(1,2))

// Initial set parameters
l('12. 28. 2.667 0.0007')
```



Working with the identical logic of route objects, coding using the Gibberwocky Max package.  The addition of jit.gl.sketch complements my research initiative to explore various approaches to writing glsl (or pseudo glsl) code, visually.  sigv then now supports the idea of composing with glsl through the the jit.gl.pix/jit.gl.slab and jit.gl.sketch objects.



### sigv-hydra

After exploring an exhaustive list of live coding languages, environments, and technologies, in addition to preferring the unique Orca and Gibberwocky environments, I have also been significantly drawn to Hydra.  Its syntax, flow, and operator logic seems to attract me in ways that made me want to find ways in which I can have it's language integrate with sigview's route objects.



### sigview-lc-av

Moving beyond the oscilloscope concept, and to include the coding inside of the environment, as opposed to external messaging.  Coding leveraged by a network of route objects and the th.gl.commandline package.



### sigview / sigview-light (original)

First version of these experiments focused on the making of an oscilloscope-like instrument for simply visualizing audio signals.  The objectives were to (1) display a center wave, and (2) a 2D grid, all within a 3D environment allowing for live coded transformations of both items together or independently.  Live code environment used with sigview in these experiments was a custom Gibberwocky MIDI.



## Rationale

Composition Experiment: *Trilingual*

<iframe width="560" height="315" src="https://www.youtube.com/embed/pH0c0DU4gSI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

This composition combined three live coding languages modulating a simple Hydra shape via MIDI CC messages from Gibberwocky, while music is sequenced in Orca.  My thoughts during the making of this was to imagine the various ways in which the signals can be monitored through live coding its visual representations.  It was this thinking that brought me to wanting to create a system that allowed this to happen and be embedded in future live performances.  

