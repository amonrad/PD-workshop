# PD-workshop

This folder contains a number of abstractions, developed for sound synthesis in the pure data programming language. Also included is a pdf-file (PD workshop - slides) with a short introduction written in Danish.

Within Pure data, create a path to this folder in preferences to use the abstractions for your own pure data-projects - or simply save a new file in the same folder and use the abstractions here. To use the abstractions you create a new object in your pd-patch and type in the name of the abstraction you want to use.

Documentation for the individual abstractions is written within the abstractions if you open them in Pure data. Documentation is also listed here:


//———————————————--------------------------------//

ADSRenvelope

Inlets:
1 number (0-127), velocity in from midi-input
2 number (1-1000), attack
3 number (1-1000), decay
4 number (1-100), sustain
5 number (1-3000), release

Outlets:
1 signal, ADSR-envelope out

//———————————————--------------------------------//

AudioOnOff

Inlets: 
1 toggle Audio processing On or Off (accepts zero or non-zero number value)


//———————————————--------------------------------//

bpm

Description:
Calculates bpm-value (beats pr minute) into milliceconds between successive metro-beats. Outputs beats from specified bpm-value, like old-fashioned metronome.

Inlets:
1 number (20-600), bpm value
2 toggle (0-1), turn metro on/off

Outlets:
1 number, metronome out
2 toggle out

//———————————————--------------------------------//

Envelope

Inlets:
1 Bang-message, trigger envelope
2 number, set envelope duration in milliseconds (1-20000)

Outlets:
1 signal, outputs specified envelope

//———————————————--------------------------------//

Equalizer

Description:
Using Fourier resynthesis you can take an incoming sound, operate on its spectrum (by drawing the frequency envelope in the window), and hear the result. The window ranges from 0-22000 hertz on the x-axis, and 0-2 amplitude on the y-axis.

Inlets:
1 Signal in

Outlets:
1 Signal out

//———————————————--------------------------------//

Modus

Description: Modus-object: transforms chromatic midipitch-input to specified modus.

Inlets:
1 number (0-127), midiPitch in
2 number (0-11), specify modus
3 number (3-6), transpose midipitch-output to specified octave

Outlets:
midi-pitch in specified modus and octave out

//———————————————--------------------------------//

Panner

Inlets:
1 number (0-127), specifies stereo-panning (64 is middle)
2 signal, left channel
3 signal, right channel

Outlets:
1 signal, left channel
2 signal, right channel

//———————————————--------------------------------//

Reverb3

Inlets:
1 signal, left channel
2 signal, right channel
3 number (0-100), output level
4 number (0-100), liveness
5 number, crossover freq. in hertz
6 number (0-100), high freq. damping
7 number (0-100), wet mix
8 number (0-100), dry mix)

Outlets:
1 signal, left channel
2 signal, right channel

//———————————————--------------------------------//

Reverberator

Inlets:
1 signal, left channel
2 signal, right channel
3 number (0-100), feedback gain to control reverb time
4 number (0-100), wet mix
5 number (0-100), dry mix

Outlets:
1 signal, left channel
2 signal, right channel

//———————————————--------------------------------//

Sampler

Inlets:
1 signal, audio in
2 bang, open existing soundfile
3 toggle, record soundfile
4 number, specify duration in milliseconds
5 bang, play sample
6 number (float), specify playback speed (0.1-4, 1 is normal speed)
7 number, specify starting point of playback (0-100)

Outlets:
1 signal, audio out

//———————————————--------------------------------//

showFreqDomain

Description: This abstraction computes the spectrum of the incoming signal with a (rectangular windowed) FFT.

Inlets:
1 signal in to be analyzed
2 toggle on/off

//———————————————--------------------------------//

showWave

Description: live-display (waveform) of incoming signal

Inlets: 
1 signal in to be displayed
2 number (1-100), render frequency
3 toggle on/off

//———————————————--------------------------------//

simpleStepSequencer

Inlets:
1 toggle on/off
2 number, bpm
3 list of 8 numbers, preset

Outlets:
1 midi-output (note/velocity pairs)

//———————————————--------------------------------//

StepSequencer1

Inlets:
1 bang, trigger one period
2 number (100-6000), time in milliseconds of one period
3 number (2-28), specify amount of steps in one period
4 list of numbers, preset

Outlets:
1 sequencer output

//———————————————--------------------------------//

StepSequencer2

Inlets:
1 bang, trigger one period
2 number (100-6000), time in milliseconds of one period
3 number (2-16), specify amount of steps in one period
4 bang, output presets
5 list of numbers, preset note values
6 list of numbers, preset velocity values

Outlets:
1 sequencer output (note/velocity-pairs)
2 output list of note-presets
3 output list of velocity-presets

//———————————————--------------------------------//

SynthAcid

Inlets:
1 midi-input (note/velocity-pairs)
2 number (1-500), set filter resonance
3 number (1-40), set filter offset
4 number (0-1000), set filter time
5 number (0-1000), set filter scale
6 number (50-1000), set decay time

Outlets:
1 Synth output

//———————————————--------------------------------//

SynthClap

Inlets:
1 midi-input (pitch/Velocity-pair)
2 number (1-5000), cutoff
3 number (1-5000), width
4 number (1-25), delay
5 number (1-25), decay
6 number (0-3), preset

Outlets:
1 signal out

//———————————————--------------------------------//

SynthCymbal

Inlets:
1 midi-input (pitch/Velocity pairs)
2 number (1-1000), decay
3 number (1-10000), pitch
4 number (0-3), preset

Outlets:
1 signal out

//———————————————--------------------------------//

SynthFM

Inlets:
1 midi-input (note/velocity pairs)
2 number (0-7), preset

Outlets:
1 signal out

//———————————————--------------------------------//

SynthFormant-Bank

Description: formantfilters simulating vowel sounds, works with incoming signal to be filtered - works best with Pulsetrain-signal

Inlets:
1 signal in, to be filtered
2 number (0-7), vocal formant
3 number (0-7), vocal formant
4 number (0-127), interpolation between vocal 1 & 2
5 number (0-100), formantBase

Outlets:
1 signal out

//———————————————--------------------------------//

SynthFormant-PulseTrain

Inlets:
1 number (0-127), midi-pitch in
2 number (0-1000), portamento
3 number (1-99), pulseWidth
4 number (0-20), vibratoFreq
5 number (0-20), vibratoDepth
6 number (0-1), voice on/off

Outlets:
1 signal, pulsetrain out

//———————————————--------------------------------//

SynthGuitar

Inlets:
1 midi-input (note/Velocity pairs)
2 number (1-40), width
3 number (0.9-0.999), decay
4 number (100-8000), cutoff
5 toggle (0-1), excitation (noise/partial)
6 number (1-16), enhance Partial number for excitation

Outlets:
1 signal out

//———————————————--------------------------------//

SynthKickdrum

Inlets:
1 midi-input (pitch/velocity pairs)
2 number (1-2000), decay
3 number (0-20), pitchScale
4 number (0-20), filterScale
5 number (0-50), sineScale
6 number (0-4), preset

Outlets:
1 signal out

//———————————————--------------------------------//

SynthRissetsBell

Description:
Implementation of a simple additive synthesis instrument originally from Jean-Claude Risset - using 11 partials to model a bell-sound.
Partial takes as arguments an amplitude, a relative frequency, a detuning frequency, and a relative duration.

Inlets:
1 midi-input (pitch/velocity pairs)
2 number (0-20000) duration in milliseconds

Outlets:
1 signal, audio out

//———————————————--------------------------------//

SynthSnaredrum

Inlets:
1 midi-input (pitch/velocity pairs)
2 number (10-2000), decay
3 number (5-10000), noise
4 number (0-3), preset

Outlets:
1 signal out

//———————————————--------------------------------//

Test1 (simple synth)

//———————————————--------------------------------//

Test3 (random melody)

//———————————————--------------------------------//

Test4 (Step-sequencers + sampler)

//———————————————--------------------------------//

Test5 (guitarSynth with equalizer)

//———————————————--------------------------------//

Test6 (Laser + recordSound)

//———————————————--------------------------------//

Test7 (Formant-Syntese)

//———————————————--------------------------------//

waveGenerator

Inlets:
1 signal or number, frequency in
2 number (0-8), preset (selects type of waveform)

Outlets:
1 signal out

//———————————————--------------------------------//
