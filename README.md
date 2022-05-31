# GameMaker Timer
A simple timer that can count in frames, miliseconds, seconds and minutes. It's something to expand the built in alarm system

```
room_speed (frames) = 1 s
1 s = 1000 ms
1 m = 60 s
```
#### FUNCTIONS
`set_timer(<id>, <num>, <type>, <wait>)`
- id - real/string
- num - number of frames/delay
- type - frames/milliseconds/seconds/minutes (optional, default: TMR.f)
- wait - wait until this timer has finished (optional, default: false)

`times_up(<id>)` - fires once when the time runs out

`timer_finished(<id>)` - if a timer is running or not

`timer_pause(<id>)`

`timer_resume(<id>)`

`timer_pause_all()`

`timer_resume_all()`
##
The `times_up` func should be called in a step/draw event 
##
#### Possible types:
- TMR.f - frames
- TMR.ms - milliseconds
- TMR.s - seconds
- TMR.m - minutes

### EXAMPLES

```
// ------ CREATE EVENT ------ //
set_timer(1, 40);

// ------ STEP EVENT ------ //
if times_up(1) {
  show_debug_message("now"); // called after 40 frames
}
```
```
// ------ CREATE EVENT ------ //
set_timer(2, 10, TMR.s);

// ------ STEP EVENT ------ //
if times_up(2) {
  show_debug_message("now"); // called after 10 seconds
}
```
```
// ------ STEP EVENT ------ //
set_timer(3, 1, TMR.s, true);
if times_up(3) {
  show_debug_message("now"); // being called every second
}
```
