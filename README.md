# clyphx-osc

_it's just like ClyphX but w/ OSC_

## Usage

### Trigger Action

Fork of the good old ClyphX (for more info see [here](https://github.com/ldrolez/clyphx-live10/)).
No idea where I got the original source from though.

Supports triggering actions by sending an osc message to port 9000 like this:
```
/clyphx/trigger METRO "2/PLAY 3" ETC
```

It will respond with a osc message sent to localhost:9001
```
/remix/oscserver/info METRO 
/remix/oscserver/info "2/PLAY 3"
```
and if it doesn't know what to do with your message it will also send a confused:
```
/remix/oscserver/unknown ETC
```

### Query Tracklist

You can inquire about the sets track list by sending an empty message to:
```
/clyphx/info/tracks
```

If the track list changed since the last time you asked about it the server will respond with:
```
/clyphx/info/tracklist/changed 1
```

And then with multiple messages for each track in the set with the information `ID NAME TYPE`. For example:
```
/clyphx/info/tracklist 1 1-MIDI MIDI
/clyphx/info/tracklist 2 2-Audio AUDIO
/clyphx/info/tracklist 3 3-Audio AUDIO
/clyphx/info/tracklist 4 4-Audio AUDIO
/clyphx/info/tracklist 5 5-MIDI MIDI
/clyphx/info/tracklist 6 6-Audio AUDIO
/clyphx/info/tracklist A A-Reverb AUDIO
/clyphx/info/tracklist B B-Delay AUDIO
/clyphx/info/tracklist MST Master AUDIO
```

If the track list didn't change, none of the above will happen instead the server will just send the following response:
```
/clyphx/info/tracklist/changed 0
```

## Installation

Drop the contents of this directory in your MIDI Remote Scripts folder. 

For more info see: https://help.ableton.com/hc/en-us/articles/209072009-Installing-third-party-remote-scripts
