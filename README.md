# clyphx-osc

_it's just like ClyphX but w/ OSC_

## About

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

## Installation

Drop the contents of this directory in your MIDI Remote Scripts folder. 

For more info see: https://help.ableton.com/hc/en-us/articles/209072009-Installing-third-party-remote-scripts