# Making music

```package
core
radio
microphone
```

```blocks
```
```template
```


## Step 0 @showDialog
Hi! Let`s learn to make music with the Micro:bit!

## Step 1 @showHint
### Make some noise!
All the blocks needed to create sound are located inside the ``||music.music||`` category in your toolbox.
Find a ``||music.play tone||`` block and add it to your program inside the ``||basic.on start||`` block.
```blocks
music.playTone(262, music.beat(BeatFraction.Whole))
```
## Step 2 @showDialog
### Tone, beat, and tempo
Musicians use special language when describing music. Let's explore!

`Tone` refers to the piano key a note sounds like and how high or low the note is.
  
`Tempo` refers to the speed of the music. Normally, the tempo lies somewhere between 40 and 200 beats per minute (bpm). The standard tempo is 120 bpm. The higher the tempo, the faster the music is played.
  
A `beat` is the length of a single full note. The Micro:bit can play notes from 1/16 beat to 4 beats.

## Step 2 @showDialog
### How to make music
Music consists of notes and pauses between the notes. These are the blocks that will help you to create your own music:

A ``||music.play tone||`` block plays a note in a specified tone for a specified length of time in beats.
```block
music.playTone(262, music.beat(BeatFraction.Whole))
```
  
A ``||music.rest||`` block inserts a pause for a specified length of time in beats.
```block
music.rest(music.beat(BeatFraction.Whole))
```
## Step 3 @showHint
### A popular song
Let's try making music! Repeat the example code and then download it to the Micro:bit. Can you guess the song?
  
Try adding more notes and pauses to continue the song for longer!
```blocks
music.playTone(262, music.beat(BeatFraction.Whole))
music.rest(music.beat(BeatFraction.Sixteenth))
music.playTone(262, music.beat(BeatFraction.Whole))
music.rest(music.beat(BeatFraction.Sixteenth))
music.playTone(392, music.beat(BeatFraction.Whole))
music.rest(music.beat(BeatFraction.Sixteenth))
music.playTone(392, music.beat(BeatFraction.Whole))
music.rest(music.beat(BeatFraction.Sixteenth))
music.playTone(440, music.beat(BeatFraction.Whole))
music.rest(music.beat(BeatFraction.Sixteenth))
music.playTone(440, music.beat(BeatFraction.Whole))
music.rest(music.beat(BeatFraction.Sixteenth))
music.playTone(392, music.beat(BeatFraction.Double))
```

## Step 4 @showDialog
### Melodies and sounds
The Micro:bit has some ready-made sounds to choose from. These can be played with ``||music.start melody||`` and ``||music.play sound||`` blocks.
No two sounds or melodies can be played at the same time, but sounds can be played on top of melodies.

A ``||music.start melody||`` block plays a chosen melody. It provides the option to repeat a melody forever or make it a background melody that will continue playing even after it's interrupted by another melody.
```block
music.startMelody(music.builtInMelody(Melodies.Funk), MelodyOptions.Forever)
```
  
A ``||music.play sound||`` block plays a sound.
```block
soundExpression.hello.play()
```
  
A ``||music.stop all sounds||`` block stops all sounds and melodies.
```block
music.stopAllSounds()
```
## Step 5 @showHint
### Melodies and sounds
Let's try making some noise! This example code uses both melodies and sounds. Download it to the Micro:bit and press the buttons to mix melodies and sounds! 
```blocks
input.onButtonPressed(Button.A, function () {
    soundExpression.hello.play()
})
input.onButtonPressed(Button.B, function () {
    soundExpression.happy.play()
})
music.startMelody(music.builtInMelody(Melodies.Funk), MelodyOptions.Forever)

```
## Step 6 @showDialog
### Push the tempo!
We can use ``||music.set tempo||`` and ``||music.change tempo||`` blocks to affect the playback speed.
  
This block sets the tempo in beats per minute.
```block
music.setTempo(120)
```
  
This block increases the tempo by a specified number. If the number is negative, the tempo is decreased instead. 
```block
music.changeTempoBy(5)
```
```block
music.changeTempoBy(-5)
```

## Step 7 @showHint
### A metronome
Musicians use metronomes to produce a steady rhythm to assist with practice. Let's make our own metronome! All the code needed is shown in the example.
```blocks
input.onButtonPressed(Button.A, function () {
    music.changeTempoBy(-5)
})
input.onButtonPressed(Button.B, function () {
    music.changeTempoBy(5)
})
music.setTempo(120)
basic.forever(function () {
    music.playTone(523, music.beat(BeatFraction.Half))
    music.rest(music.beat(BeatFraction.Half))
    music.playTone(262, music.beat(BeatFraction.Half))
    music.rest(music.beat(BeatFraction.Half))
    music.playTone(262, music.beat(BeatFraction.Half))
    music.rest(music.beat(BeatFraction.Half))
    music.playTone(262, music.beat(BeatFraction.Half))
    music.rest(music.beat(BeatFraction.Half))
})
```

## Step 8 @showHint
### Now it's your turn
There's one more music block we haven't told you about: the ``||music.play melody||`` block. Can you try and figure it out for yourself?
```block
music.playMelody("- - - - - - - - ", 120)
```

## Step 9
Now you know some musical terminology and can play music with your Micro:bit. Awesome!
