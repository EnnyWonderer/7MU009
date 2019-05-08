# 7MU009

## Sound layer Colour Conversion 

Converts an audio signal into colours based on frequency and harmonics and displays them as particles.

---
## Background

Visual aids have been useful within music production , although arguably it takes away from focusing on what our ears can hear, they have changed the way in which many users perceive the behaviour of a sound. The spectrum analyser as an example allows listeners to easily identify fundamental frequencies and resonances or balance a mix. Another use of the spectrum analyser is measuring the frequency response of a room with the utilisation of white/pink noise and a microphone. While this use of display works for providing information for technical processes, the same informance could be displayed providing more creative information. 

Synesthesia, taken from the Greek words syn meaning ‘together’, and aesthesis meaning ‘perception’, is "sensation in one part of the body produced by stimulus in another," (online etymology dictionary 2018). In this case, Seeing Sounds as shapes and colors (Chromesthesia) As Goldsmith points out “no common set of color and sound associations exist between individual synesthetes. Synesthesia is a personal experience and the details of the perceptions are completely subjective” and so there is no overall way to represent this for all synesthetes to see as accurate. What can be taken from this is that, like synesthetes, we can use technology to be given a new sensation when hearing sounds, through the use of shapes and colours.

![text](https://camo.githubusercontent.com/a0abf636697a008167197185de5c325e8905096f/68747470733a2f2f696d672e796f75747562652e636f6d2f76692f55493465714f50324155302f302e6a7067)

This project takes inspiration from CNLohr's Chromatic sound to light conversion system which not only takes a sound source and displays a colour based on the frequency of the sound, but it also does this process for harmonics found displayed them all on a voronoi diagram relative to the amplitude of each spike in frequency. The idea of also displaying harmonics has been taken and used at a high sensitivity to display as many harmonics as possible giving a wide potential variety of colours. because of this they are being displayed as particles linked again to the amplitude to provide information on how many frequencies are building up to that total sound/timbre.

---
## MIDI vs OSC 

"Application areas for MIDI include music, lighting control, show control (and themed events), machine control (audio and video), robotics, and more" (TMA)
While it would enable us a reasonable set of control and information to take from sound MIDI is primarily a language of predefined messages meaning that it might not be adaptable to the range of existing instruments and how they are played while OSC is completely customisable. TMA (The Midi Association) argues "any software or hardware manufacture may obtain a unique ID that enables them to create System Exclusive messages which can have any structure and use any data format" however this still applies to a language while this project aims to work with audio. The signal would have to be converted into MIDI before being able to utilise it taking away the option of microtuning etc. To keep up with the different behaviours of sound it may be more suitable to use OSC and customise it to process multiple variations of information.

---
## How it was made


The process was done in three stages:

- recieving audio and dissecting harmonics and thier amplitudes
- processing pitch and converting to a colour
- displaying the pitches and their relative amplitude as particles

This was layed out as a building block format for ease of use and to potentially allow for more blocks for additional functions. 

According to Goss (2016) the vibrations of sound and light differentiate as sound is based on vibrations of air molecules and light is based on an electromagnetic wave. While “frequency” is a measure commonly used for both, the two types of waves have substantial differences. frequency of sound can be converted to a frequency of light by continuously doubling the sound frequency (going up one octave each time) until it reaches a frequency in the range of 400–800 THz. That frequency is then converted into a wavelength of light, using the formula:
wavelength = speedOfLight / frequency. I wasn't quite sure how to convert this into an rgb value and so search for any insight online

For the colour conversion an existing Pd patch by user Sunji who built a patch that took a midi number  and gave it a colour value based around synesthesiac historic figures Wassily Kandinski and Alexander Scriabin. While it give a consistent colour per octave for each note, it was not clear in which way the link was made to Scriabin unless it was to combine some of Sciabin's notes with Kandinski's it was also noticeable that if the numbers were minus numbers, purples would appear but only blues when above 0, this could be due to the equation used with the cosine object. Pure data didn't prove to be the easiest approach to applying the sound-to-colour conversion.
![text](https://www.flutopedia.com/img/ScriabinKeyboard_lg.jpg)
The particle system in Pd was troublesome as trying to link different behaviours lead to responses that were too extreme E.G the speed of the particle movement would cause particles to shoot of the screen when they were needed to orbit a specific point, this meant a lot of methods to link the particle behaviour and sound behavior would be difficult to display in a sophisticated if they are intended to still be displayed on the screen. If given more time a potential solution could have been to expand the overall GEM window size and the particle size so that any movements would appear smaller.

## Improvements
This current set up is limited as it repeats over an octave. however it could potentially get a unique colour for each note if all the colours displayed were to be blended toghether.



---
## Bibliography


Goldsmith J (2001) An Investigation Into the Relationship Between Sound and Color [online]. [accessed 7th January 2019]. Available at < http://www.people.vcu.edu/~djbromle/color-theory/color01/Relationship-color-sound-joe_goldsmith.html>

Goss C (2016) The color of sound. [online]. [accessed 7th January 2019] Available at: < http://www.flutopedia.com/sound_color.htm>

Lohr C. N ColorChord Chromatic Sound to Light Conversion System [online]. [accessed 9th January 2019]. Available at: <https://github.com/cnlohr/colorchord>

Moss J (2019) 5 Ways Spectrum Analyzers Can Supercharge Your Mixes. [online]. [accessed 7th may 2019] Available at: <https://behindthespeakers.com/spectrum-analyzers-supercharge-mixes/>

The MIDI Association (2019) White Paper: Comparison of MIDI and OSC. [online]. [accessed 7th may 2019] Available at: <https://www.midi.org/articles-old/white-paper-comparison-of-midi-and-osc>
