<!--
DONE:
- gifs or screenshots (smallest possible)
TODO:
- donation link PayPal
- early developement stage info, help, support, ideas
- descriptions - in jsfx files and in README
- Plugin Doctor template, jsfx demo project, plugin chains
- Mixing template
- reaper jsfx folder cleanup - faster load times
- 4k compatibility
- new name for correlation meter and k-flanger (m-flanger, klanger, mlanger)
- rename all plugins to jm_type_name.jsfx
- logo



desc: Dual Time Adjustment
author: Michael Schnell (mschnell@bschnell.de)
version: 2.0
changelog: add positive Midi delay
donation: United Nations Foundation http://www.unfoundation.org/
about:
  ## Description

  Apply a positive or negative delay to up to two audio channel in a track and optionally to Midi

     modes:
   - Stereo: All Sliders are coupled
   - Dual: Two channels with two coupled sliders each 



desc:Saike Swellotron (No GUI, No PDC) [JM]
tags: ambient, soundscape, long, reverb, convolution, stft
version: 0.09
author: Joep Vanlier
changelog: Add about section.
about:
  # Swellotron
  Swellotron computes the spectrum of both signals (using the STFT), multiplies the magnitudes in the spectral domain and puts the result of that in an energy buffer. This energy buffer is drained proportionally to its contents. The energy buffer is then used to resynthesize the sound, but this time with a random phase.
  In plain terms, it behaves almost like a reverb, where frequencies that both sounds have in common are emphasized and frequencies where the sounds differ are attenuated. This will almost always lead to something that sounds pretty harmonic.
  [Screenshot](https://i.imgur.com/ikizwwk.gif)
  ### Demos
  You can find demos of the plugin [here](https://www.youtube.com/watch?v=PSaL8BvYdKk) and [here](https://www.youtube.com/watch?v=Ggojmb9wd5U).
  ### Features:
  - FFT Reverberation
  - Shimmer: Copies energy to twice the frequency (leading to iterative octave doubling).
  - Aether: Same as shimmer but for fifths.
  - Scorch: Input saturation.
  - Ruin: Output saturation.
  - Diffusion: Spectral blur.
  - Ice: Chops small bandwidth bits from the energy at random, and copies them to a higher frequency (at 1x or 2x the frequency), thereby giving narrowband high frequency sounds (sounding very cold).

Copyright (C) 2019 Joep Vanlier
License: MIT

-- Based on the STFT-Based Effect Template by Geraintluff
-->


<h1 align="center">Józef Maćkowiak’s REAPER Plugins</h1>

## How to Install

Add the following repository to [ReaPack](https://reapack.com):

```
https://github.com/jozmac/reapack-jm/raw/master/index.xml
```

If you’re new to this, check [this video](https://youtu.be/gVbMbqGSB7E?t=367).


<!--
# Plugins
-->

All plugins are in early developement, so parameters and functionality may change.
Please report suggestions, feature requests and bugs.


# Analysers

## Histogram
![02-05-23_reaper_477](https://user-images.githubusercontent.com/123021340/235791502-3fe553b7-01c1-4567-9570-0c766c3d230e.gif)
  Visualization of input signal distribution.
  ### Features:
  - mean, standard deviation, max and min value readouts for two channels
  - readout of values at cursor position
  - variable bin number
  - X and Y exponential scaling
  - bin decay factor

## Autocorrelation Analyser
![04-05-23_reaper_580](https://user-images.githubusercontent.com/123021340/236194317-43261a43-612a-4866-8598-aa1a5d473113.gif)
  Displays crosscorrelation function of two channels or autocorrelation of mono signal.
  ### Features:
  - auto-detect maximum in selection
  - note, distance, frequency and quefrency readout 
  - color indicating chroma of musical note

## Cepstrum Analyser
![03-05-23_reaper_509](https://user-images.githubusercontent.com/123021340/236180935-4cb80718-c082-48fc-a956-e40b41f37b9c.gif)
  ### Features similar to autocorrelation analyser

## Transfer Function Analyser
![03-05-23_reaper_517](https://user-images.githubusercontent.com/123021340/236181048-2cb60583-d540-4e64-b3b9-f2c9af9918dc.gif)

## Signal Transfer Function Analyser (STFA)
![04-05-23_reaper_537](https://user-images.githubusercontent.com/123021340/236184110-233d8a55-be28-44c8-8589-ac56882aa64c.gif)
  Features:
  - stereo analysis (route non-processed signals to channels 3/4) 
  - readout of dB value at cursor position

## Vectorscope
![04-05-23_reaper_527](https://user-images.githubusercontent.com/123021340/236181211-13e84d09-36fe-4ba7-b4b6-d83fccb4ada8.gif)

## Mean Complex Square Vectorscope
![03-05-23_reaper_499](https://user-images.githubusercontent.com/123021340/235800512-6232800b-f098-47b4-9d1f-3e0c157d4b2d.gif)
  
  Stereo signal azimuth analyser.

## Strobe Tuner
![04-05-23_reaper_529](https://user-images.githubusercontent.com/123021340/236182222-77f9db15-5edf-4bdb-9a8b-3d9f05925857.gif)

## Phase Wheel Analyser
![04-05-23_reaper_533](https://user-images.githubusercontent.com/123021340/236182943-74c2e1ab-8a47-4ab3-ae05-6c958d0cd4e2.gif)
  
  Displays phase difference between two channels (frequency => distance from center)

## Phase Wheel Analyser v2
![04-05-23_reaper_591](https://user-images.githubusercontent.com/123021340/236243032-9b31853d-0def-4f1b-8b93-ca792e36ab68.gif)
  
  The transfer function of the stereo signal from the direction of the frequency axis.

## Stereoscope
![04-05-23_reaper_543](https://user-images.githubusercontent.com/123021340/236187181-32e9eb96-016d-4dd3-a050-45fedaa93f59.gif)
  Azimuth-frequency graph of stereo signal. Usefull for calibrating analog equipment or checking correlation of partials of piano recording.
  ### Features:
  - two modes:
    - unwrapped - azimuth analysis
    - normal - similar to nebula in FLUX Analyser
  - interchannel phase difference analysis (phase difference value -> hue)
  - blur and decay factor
  - readout of azimuth and frequency at cursor position

## Coherence Analyser
![02-05-23_reaper_483](https://user-images.githubusercontent.com/123021340/235800291-17eb5f37-b503-4e2a-85a8-963a2a12fdb3.gif)
  STFT-based graphical coherence analyser.
  ### Features:
  - analysis decay factor and average time factor
  - coherence and phase graph
  - average coherence readout

## Polar Histogram
![04-05-23_reaper_551](https://user-images.githubusercontent.com/123021340/236188405-e01e7de2-9419-44e4-8381-6c3ea05e541b.gif)
   Displays stereo angle histogram
   ### Features:
   - peak, hold and energy indicator
   - variable exponential scaling

## Correlation Meter
![02-05-23_reaper_485](https://user-images.githubusercontent.com/123021340/235800419-0f8c1543-c696-4ce6-9ea1-05b242d222a0.gif)
  Correlation, balance and azimuth meter.
  ### Features:
  - variable smoothing time

## Bispectrum Analyser
![04-05-23_reaper_558](https://user-images.githubusercontent.com/123021340/236189466-c3f44d97-5f90-4720-b428-5aa5b7b1c0ad.gif)



# Effects

## Thiran Delay
![04-05-23_reaper_545](https://user-images.githubusercontent.com/123021340/236188483-258a6729-b3e8-4a9c-b70b-591de17336e1.png)
  Delay effect with allpass fractional delay algorithm.
  ### Features:
  - linked sliders with 6 unit types
  - feedback azimuth rotation
  - sidechain and sine wave delay modulation
  - parameter smoothing

## K-Flanger
![04-05-23_reaper_546](https://user-images.githubusercontent.com/123021340/236188538-83b97033-e04b-4d43-890e-656611beae66.png)
  Combination of flanger and stereo widener.
  ### Featires:
  - high quality fractional delay algorhithm
  - feedback rotation
  - three stereo widening modes

## Vowel Filter
![04-05-23_reaper_549](https://user-images.githubusercontent.com/123021340/236188601-b21d940b-4592-4c60-b9b9-09a57ce5a603.gif)

## Chebyshev Saturator
![04-05-23_reaper_587](https://user-images.githubusercontent.com/123021340/236242101-9ceb42b5-0192-42d4-a82b-c347319e6ab5.gif)
  Utility for emphasizing given harmonics.
  ### Features:
  - chebyshev polynomials from 1st to 9th order
  - harmonic mode - adjust the amount of even and odd harmonics
  - rectifier
  - DC filter
  - GFX signal transfer function wiever


## Transient Split
![04-05-23_reaper_556](https://user-images.githubusercontent.com/123021340/236189545-cc3b8e93-c1fa-4867-866c-0c3a5f9d4ed8.png)
  A tool that allows you to extract transients or stationary signals from the input signal.

## Cepstrum Lifter
![04-05-23_reaper_555](https://user-images.githubusercontent.com/123021340/236189555-152c700e-51a2-4e04-9a0c-9e20970b9aa0.png)
  ### Features:
  - long-pass, short-pass and moment-reject liftering
  - cepstrum analyser with peak detection

## STFT Extractor
![04-05-23_reaper_554](https://user-images.githubusercontent.com/123021340/236192232-a28063d3-3277-4fbf-b8f2-3d45cdad71fa.png)
  Utility for attenuating partials with given azimuth and phase difference in stereo field.


## Coherent Extractor
![04-05-23_reaper_553](https://user-images.githubusercontent.com/123021340/236189788-b1079010-493e-4974-81f5-20e3a00d3c2d.png)
  A tool for separating a coherent signal from a stereo signal.
  ### Features:
  - averaging factor
  - suppression factor

## STFT Frequency Shifter
![04-05-23_reaper_552](https://user-images.githubusercontent.com/123021340/236194913-11a5a454-f7d9-42d0-b8dd-483b7b9a874c.png)
  ### Features:
  - FFT brickwall antialiasing filter
  - linear phase processing
  - spectrum reverser
  - pre-differentiator
  - parameter smoothing

## IIR Phaser
  Phaser based on IIR Hilbert transformer with three stereo widening modes



# Generators

## Logistic Noise Generator
![04-05-23_reaper_570](https://user-images.githubusercontent.com/123021340/236191867-5ee7c738-0fd5-40b0-a4d3-957816a89346.gif)
  Noise generator based on the logistic map equation.

## Stern-Brocot Stereochord
![04-05-23_reaper_572](https://user-images.githubusercontent.com/123021340/236191889-dad9fc18-2a51-4eca-8bb1-6b85997f027c.gif)
  Triad generator with two-dimansional snap-to-integer-ratio control panel.
  ### Features:
  - simplest integer ratio snapping with variable error value 
  - multiple waveforms to choose from
  - oscilator frequency smoothing
  - ratio and frequency readouts

## Farey Tetrad Spiral 
![04-05-23_reaper_574](https://user-images.githubusercontent.com/123021340/236191959-bc89c8d1-4c56-491e-a5d2-69ab7207d078.gif)
  Four-oscillator generator with spiral visualization.
  ### Features:
  - visualization of combination tones (F1-F2, 2*F1-F2, F1-2*F2)
  - colors indicating chroma of musical note
  - display of overtones, undertones, upper and lower Farey sequences 
  - frequency readout for every tone and combination tone
  - parameter smoothing
  - multiple waveforms

## DPOAE Canceller
![04-05-23_reaper_597](https://user-images.githubusercontent.com/123021340/236298587-64f227c4-2efe-48ab-b30b-b5c55311ac98.gif)
  Generator of two periodic signals and three phase-locked signals for canceling otoacoustic emissions (F1-F2, 2*F1-F2, F1-2*F2).
  ### Features:
  - three methods of changing frequency
  - tone and combination tone visualization
  - visualization of undertones and overtones of main two tones



# Utilities

## Crossfeed
![04-05-23_reaper_560](https://user-images.githubusercontent.com/123021340/236190142-a5ee30ed-8329-429b-b260-e5e071a0a0e2.gif)
  Utility plugin inspired by the Goodhertz CanOpener
  ### Features:
  - three crossfeed algorhithms
  - delay value readouts
  - speaker angle visualization

## Proximity Processor
![04-05-23_reaper_562](https://user-images.githubusercontent.com/123021340/236191716-ac359225-08fa-4e7c-8922-288352cef26d.gif)
  A tool for positioning sound object in stereo field.
  ### Features:
  - easy to use, MCP dockable GUI
  - two modes of ITD (delay and pseudo-delay)
  - distance-dependent reverb send gain
  - parameter smoothing

## Stereo Tool
![04-05-23_reaper_564](https://user-images.githubusercontent.com/123021340/236191762-829398cc-ed97-4279-8359-2477347fd318.gif)
Utility for modyfying azimuth, balance and width of stereo field.










<!--
## Multicam Editing

<h3 align="center"><a href="https://youtu.be/1BvuRgKNnqc">Watch the video with a demonstration and instructions!</a></h3>

Install the FX Chains:

- [`FXChains/leafac_Video processor - Multicam - Preview.RfxChain`](FXChains/leafac_Video%20processor%20-%20Multicam%20-%20Preview.RfxChain)
- [`FXChains/leafac_Video processor - Multicam - Selector.RfxChain`](FXChains/leafac_Video%20processor%20-%20Multicam%20-%20Selector.RfxChain)

## Automixer

<h3 align="center">Watch the videos with demonstrations and instructions!</h3>

- [Quick start](https://youtu.be/hSnk6ueU3hQ).
- [Main features](https://youtu.be/qi1jQcIaOxo).
- [Automixer video editor](https://youtu.be/aEvO3ufOqvY).

See also:

- [Code review](https://youtu.be/7V2dGYGtV-8).
- [Example projects](https://archive.org/download/leafac/leafac_Automixer%20Examples.zip).
- [Automixer video editor FX Chain](FXChains/leafac_Video%20processor%20-%20Automixer.RfxChain).


Even more information:

- Alternatives:
  - [The original REAPER JSFX extension on which this is based](https://forum.cockos.com/showthread.php?t=173289). It doesn’t have as many features (for example, track priorities), and is more prone to bugs because it relies on inter-plugin communication. But it’s easier to setup for simple cases and it supports projects with massive numbers of tracks, while this modification is limited by the 64 channels per track that REAPER offers.
  - [TBProAudio’s AMM Automatic Microphone Mixer](https://www.tb-software.com/TBProAudio/amm.html). It’s limited to 16 stereo tracks and requires a setup with transmitters and receiver plugin instances, which limits the possibility of having independent groups of automixed tracks.
  - [WTAUTOMIXER](https://www.wtautomixer.com).
  - [Waves Dan Dugan Automixer Plugin](https://www.waves.com/plugins/dugan-automixer). This only works on Waves MultiRack system, not as a regular audio plugin.
- Papers on Automixers:
  - [Real-Time Multi-Track Mixing For Live Performance](https://zenodo.org/record/2550903#.X43irC9h01I).
  - [Automatic Microphone Mixer White Paper](https://jp.yamaha.com/files/download/other_assets/7/329527/Automixer_WhitePaper_en.pdf).
  - [The original patent](https://worldwide.espacenet.com/publicationDetails/originalDocument?CC=US&NR=3992584A&KC=A&FT=D&ND=&date=19761116&DB=&locale=en_EP). This patent has expired, and since then the Automixer is also known as a **gain sharing algorithm**.
  - [An article explaining how to Automixer works on a high level](http://www.protechaudio.com/products/PDFFiles/DuganMixing.pdf).
- How I learned about Automixing:
  - [Podigy’s Complete Guide to Podcast Editing](https://podigy.co/podcast-editing-guide/). This where I first read about Automixing and became obsessed with the topic.
  - [An interview on the Podcast Engineering School with Dan Dugan, the inventor of the Automixer](https://podcastengineeringschool.com/dan-dugan-inventor-of-the-automatic-microphone-mixer-pes-101/).

-->

## Third-Party ReaPack Redistribution

| Extension                                                                                               | Author                                                                        | Repository Index URL                                                          |
| ------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ----------------------------------------------------------------------------- |
| **All**                                                                                                 |                                                                               | `https://github.com/jozmac/reapack-jm/raw/master/ThirdParty/index.xml`            |
| [Tale's JSFX Pack](https://www.taletn.com/reaper/)                                                                         | Theo Niessink  | `https://github.com/jozmac/reapack-jm/raw/master/ThirdParty/Tale/index.xml`        |
| [CookDSP Library](http://ajaxsoundstudio.com/cookdspdoc/)                                 | [Olivier Belanger](http://olivier.ajaxsoundstudio.com/)                        | `https://github.com/jozmac/reapack-jm/raw/master/ThirdParty/cookdsp/index.xml`       |
| [ABLevelMatching, AutoGainStaging, and EBUR128LM](https://www.tb-software.com/TBProAudio/download.html) | [TBProAudio](https://www.tb-software.com/TBProAudio/index.html)               | `https://github.com/jozmac/reapack-jm/raw/master/ThirdParty/TBProAudio/index.xml` |



<!--
Thanks to the entire REAPER community, and in particular to:

Justin Frankel (Cockos)
John Schwartz (Schwa)
Theo Niessink (Tale) (https://www.taletn.com/reaper/mono_synth/)
Justin Johnson (nitsuj)
Leandro Facchinetti (leafac)
Geraint Luff (https://signalsmith-audio.co.uk/)
Joep Vanlier (Sai'ke)
TBProAudio
Sonic Anomaly
ATK Community and Joseph Anderson, Josh Parmenter, Trond Lossius (https://www.ambisonictoolkit.net/documentation/reaper/)
Philip S. Considine (IX)
Thierry Rochebois (TiaR)
Kite Giedraitis (TallKite)
micsthepick (https://github.com/micsthepick)
ccernn (https://sites.google.com/site/ccernnaudio/js-plugins) (cern.th.skei)
SaulT
kawa (https://www.kawa.works/)
LOSER
Sexan
chokehold
Liteon
jahudka (https://github.com/jahudka?tab=repositories)
micsthepick (https://github.com/micsthepick)

Merlijn van Veen (https://www.merlijnvanveen.nl/en/)
Aleksey Vaneev (https://www.voxengo.com/)
Robin Schmidt (http://www.rs-met.com/)
Dan Worrall
Bob Katz (https://www.digido.com/)
Robert Bond Randall (B&K Frequency Analysis)
Siegfried Linkwitz (https://www.linkwitzlab.com/index.htm)
Wiliam M. Hartmann (Signals, Sound, and Sensation)
-->
