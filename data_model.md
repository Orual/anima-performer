

#### Characteristics:
* Single-Note:
    * pitch
    * timing
    * duration
        * articulation
            * staccato
            * tenuto
            * fermata
    * ornaments
* Multi-Note:
    * bar
    * tempo
    * key
    * chord
    * legato
    * pedal

#### Conversion Procedure
1. Pair each MIDI note with MusicXML equivalent
    * Iterate through the internal representation of each in sequence
    * if pitch matches and timing is closest of surrounding 16 notes, associate them
    * if pitch doesn't match, keep trying subsequent midi notes until one does
        * this should keep ornaments from tripping up the process
        * associate ornaments with the matched note closest to them in time
2. Associate duration + velocity and articulations for each paired note
3. Associate ornament marking with any ornament MIDI notes + durations + velocities
