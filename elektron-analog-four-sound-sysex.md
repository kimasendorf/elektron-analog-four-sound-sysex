# Elektron A4 Sound SysEx

#### Meta

* Header -> 0-23 -> 24 Bytes
* Name -> 24-40 -> 17 Bytes (26 = 0x00; 34 = 0x00)


#### Header

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Program Number | | 09 | 1 | 00 | 00 | ff | 256 Sounds |


#### Footer

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Checksum | | 410 | 2 | 00 00 | 00 00 | 7f 7f | Sum of all Bytes from 10 to 409 |
| File Size | | 412 | 2 | 03 15 | 03 15 | 03 15 | Fixed length of 415 Bytes |
| End Marker | | 414 | 1 | 7f | 7f | 7f | Last Byte |


#### OSC1

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Coarse Tune | TUN | 43 | 1 | 40 | 00 | 7f | -63 to +63 |
| Fine Tune | FIN | 44 | 1 | 00 | 00 | 7e | -64 to -1 and 0 to +63 |
| Fine Tune +/- | FIN | 42 | 1 | 00 | 00 | 20 | 20 = -Range; 00 = +Range |
| Detune | DET | 47 | 1 | 40 | 00 | 7f | -64 to +63 |
| Key Track | TRK | 52 | 1 | 01 | 00 | 01 | Off/On |
| Level | LEV | 56 | 1 | 64 | 00 | 7f | 0 to 127 |
| Wave Shape | WAV | 61 | 1 | 00 | 00 | 07 | 8 Wave Shapes |
| Sub Oscillator | SUB | 65 | 1 | 00 | 00 | 04 | Off and 4 Options |
| Pulse Width | PW | 70 | 1 | 40 | 00 | 7f | -64 to +63 |
| PWM Speed | SPD | 75 | 1 | 0a | 00 | 7f | 0 to 127 |
| PWM Depth | PWM | 79 | 1 | 00 | 00 | 7f | 0 to 127 |
| Amplitude Modulation | AM1 |  97 | 1 | 00 | 00 | 01 | Off/On |


#### NOISE

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Sample & Hold | SNH | 91 | 1 | 00 | 00 | 7f | 0 to 127 |
| Color | COL | 271 | 1 | 40 | 00 | 7f | -64 to +63 |
| Fade | FAD | 93 | 1 | 40 | 00 | 7f | -64 to +63 |
| Level | LEV | 95 | 1 | 00 | 00 | 7f | 0 to 127 |


#### OSC2

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Coarse Tune | TUN | 45 | 1 | 40 | 00 | 7f | -63 to +63 |
| Fine Tune | FIN | 46 | 1 | 00 | 00 | 7e | -64 to -1 and 0 to +63 |
| Fine Tune +/- | FIN | 42 | 1 | 00 | 00 | 08 | 08 = -Range; 00 = +Range |
| Detune | DET | 49 | 1 | 40 | 00 | 7f | -64 to +63 |
| Key Track | TRK | 54 | 1 | 01 | 00 | 01 | Off/On |
| Level | LEV | 59 | 1 | 00 | 00 | 7f | 0 to 127 |
| Wave Shape | WAV | 63 | 1 | 00 | 00 | 07 | 8 Wave Shapes |
| Sub Oscillator | SUB | 68 | 1 | 00 | 00 | 04 | Off and 4 Options |
| Pulse Width | PW | 72 | 1 | 40 | 00 | 7f | -64 to +63 |
| PWM Speed | SPD | 77 | 1 | 25 | 00 | 7f | 0 to 127 |
| PWM Depth | PWM | 81 | 1 | 00 | 00 | 7f | 0 to 127 |
| Amplitude Modulation | AM2 | 100 | 1 | 00 | 00 | 01 | Off/On |


#### VIBRATO

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Speed | SPD | 116 | 1 | 20 | 00 | 7f | 0 to 127 |
| Depth | VIB | 118 | 1 | 40 | 00 | 7f | 0 to 127 |
| Fade | FAD | 113 | 1 | 40 | 00 | 7f | -64 to +63 |
| Bend Depth | BND | 107 | 1 | 40 | 00 | 7f | -64 to +63 |


#### SLIDE

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Slide Time | SLI | 109 | 1 | 20 | 00 | 7f | 0 to 127 |
| Legato | | 283 | 1 | 00 | 00 | 01 | Off/On (Sound Menu) |
| Mode | | 281 | 1 | 02 | 00 | 02 | Off/On/Legato (Sound Menu) |


#### SYNC

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Sync Amount | SNC | 104 | 1 | 7f | 00 | 7f | 0 to 127 |
| OSC Restart | TRG | 111 | 1 | 00 | 00 | 01 | Off/On |
| OSC Drift | | 280 | 1 | 01 | 00 | 01 | Off/On (Default seems to be 01?) |
| Mode | SMD | 102 | 1 | 00 | 00 | 03 | Off/1->2/2->1/Metal |


#### LP-Filter

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Frequency | FRQ | 120 | 2 | 7f 00 | 00 00 | 7f 00 | 0.0 to 127.0; 0.10 = floor(10*2.56) = 0x19 |
| Freq Decimal Factor | FRQ | 114 | 1 | 00 | 00 | 01 | 0.00-0.49 = 0x00; 0.50-0.99 = 0x01 |
| Resonance | RES | 123 | 1 | 14 | 00 | 7f | 0 to 127 |
| Overdrive | OVR | 125 | 1 | 40 | 00 | 7f | -64 to +63 |
| Keytrack | TRK | 127 | 1 | 40 | 00 | 7f | -64 to +63 |
| Envelope Depth | DEP | 129 | 1 | 40 | 00 | 7f | -64 to +63 |
| F1 Resonance Boost | | 285 | 1 | 01 | 00 | 01 | Off/On |


#### Filter 2

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Frequency | FRQ | 132 | 2 | 00 00 | 00 00 | 7f 00 | 0.0 to 127.0; 0.22 = floor(22*2.56) = 0x38 |
| Freq Decimal Factor | FRQ | 130 | 1 | 00 | 00 | 01 | 0.00-0.49 = 0x00; 0.50-0.99 = 0x01 |
| Resonance | RES | 134 | 1 | 0c | 00 | 7f | 0 to 127 |
| Type | TYP | 136 | 1 | 04 | 00 | 06 | 7 Filter Types |
| Keytrack | TRK | 139 | 1 | 40 | 00 | 7f | -64 to +63 |
| Envelope Depth | DEP | 141 | 1 | 40 | 00 | 7f | -64 to +63 |


#### AMP (Envelope)

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Attack | ATK | 164 | 1 | 00 | 00 | 7f | 0 to 127 |
| Decay | DEC | 171 | 1 | 40 | 00 | 7f | 0 to 127 |
| Sustain | SUS | 177 | 1 | 64 | 00 | 7f | 0 to 127 |
| Release | REL | 184 | 1 | 08 | 00 | 7f | 0 to 127 (127 = Infinite) |
| Shape | SHP | 191 | 1 | 02 | 00 | 0b | 12 Shapes (01 = 00 + Restart etc.) |
| Chorus | CHO | 145 | 1 | 00 | 00 | 7f | 0 to 127 |
| Delay | DEL | 148 | 1 | 00 | 00 | 7f | 0 to 127 |
| Reverb | REV | 150 | 1 | 00 | 00 | 7f | 0 to 127 |
| Pan | PAN | 152 | 1 | 40 | 00 | 7f | L64 to R63 |
| Amp Level | VOL | 155 | 1 | 64 | 00 | 7f | 0 to 127 |


#### Envelope (Filter)

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Shape | SHP | 187 | 1 | 02 | 00 | 0b | 12 Shapes (01 = 00 + Restart etc.) |
| Attack | ATK | 159 | 1 | 00 | 00 | 7f | 0 to 127 |
| Decay | DEC | 166 | 1 | 40 | 00 | 7f | 0 to 127 |
| Sustain | SUS | 173 | 1 | 40 | 00 | 7f | 0 to 127 |
| Release | REL | 180 | 1 | 08 | 00 | 7f | 0 to 127 (127 = Infinite) |
| Gate Length | LEN | 193 | 1 | 00 | 00 | 7f | Off, 0 to 128 (Exponential) |
| Route 1 | DST | 198 | 1 | 0c | 00 | 7f | *Routing Ids* |
| Route 1 Depth | DEP | 207 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 1 Depth Intermediate Step | DEP | 202 | 1 | 00 | 00 | 02 | 00 = 0; 02 = +1 |
| Route 1 Depth Decimal | DEP | 208 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |
| Route 2 | DST | 200 | 1 | 0d | 00 | 7f | *Routing Ids* |
| Route 2 Depth | DEP | 209 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 2 Depth Intermediate Step | DEP | 210 | 1 | 00 | 00 | 40 | 00 = 0; 40 = +1 |
| Route 2 Depth Decimal | DEP | 211 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |


#### Envelope 2 (User)

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Shape | SHP | 189 | 1 | 02 | 00 | 0b | 12 Shapes (01 = 00 + Restart etc.) |
| Attack | ATK | 161 | 1 | 00 | 00 | 7f | 0 to 127 |
| Decay | DEC | 168 | 1 | 40 | 00 | 7f | 0 to 127 |
| Sustain | SUS | 175 | 1 | 40 | 00 | 7f | 0 to 127 |
| Release | REL | 182 | 1 | 08 | 00 | 7f | 0 to 127 (127 = Infinite) |
| Gate Length | LEN | 196 | 1 | 00 | 00 | 7f | Off, 0 to 128 (Exponential) |
| Route 1 | DST | 203 | 1 | 4c | 00 | 7f | *Routing Ids* |
| Route 1 Depth | DEP | 212 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 1 Depth Intermediate Step | DEP | 210 | 1 | 00 | 00 | 10 | 00 = 0; 10 = +1 |
| Route 1 Depth Decimal | DEP | 213 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |
| Route 2 | DST | 205 | 1 | 0d | 00 | 7f | *Routing Ids* |
| Route 2 Depth | DEP | 214 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 2 Depth Intermediate Step | DEP | 210 | 1 | 00 | 00 | 04 | 00 = 0; 04 = +1 |
| Route 2 Depth Decimal | DEP | 215 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |


#### LFO 1

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Shape | SHP | 239 | 1 | 00 | 00 | 06 | 7 Shapes |
| Mode | MOD | 235 | 1 | 00 | 00 | 04 | 5 Modes |
| Start Phase | SPH | 230 | 1 | 00 | 00 | 7f | 0 to 127 |
| Fade | FAD | 225 | 1 | 40 | 00 | 7f | 0 to 127 |
| Speed | SPD | 216 | 1 | 70 | 00 | 7f | 0 to 127 |
| Multiplier | MUL | 221 | 1 | 04 | 00 | 23 | 3 x 12 Options |
| Route 1 | DST | 244 | 1 | 22 | 00 | 7f | *Routing Ids* |
| Route 1 Depth | DEP | 253 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 1 Depth Intermediate Step | DEP | 250 | 1 | 00 | 00 | 08 | 00 = 0; 08 = +1 |
| Route 1 Depth Decimal | DEP | 254 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |
| Route 2 | DST | 246 | 1 | 27 | 00 | 7f | *Routing Ids* |
| Route 2 Depth | DEP | 255 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 2 Depth Intermediate Step | DEP | 250 | 1 | 00 | 00 | 02 | 00 = 0; 02 = +1 |
| Route 2 Depth Decimal | DEP | 256 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |


#### LFO 2

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Shape | SHP | 241 | 1 | 00 | 00 | 06 | 7 Shapes |
| Mode | MOD | 237 | 1 | 00 | 00 | 04 | 5 Modes |
| Start Phase | SPH | 232 | 1 | 00 | 00 | 7f | 0 to 127 |
| Fade | FAD | 228 | 1 | 40 | 00 | 7f | 0 to 127 |
| Speed | SPD | 219 | 1 | 60 | 00 | 7f | 0 to 127 |
| Multiplier | MUL | 223 | 1 | 04 | 00 | 23 | 3 x 12 Options |
| Route 1 | DST | 248 | 1 | 22 | 00 | 7f | *Routing Ids* |
| Route 1 Depth | DEP | 257 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 1 Depth Intermediate Step | DEP | 258 | 1 | 00 | 00 | 40 | 00 = 0; 40 = +1 |
| Route 1 Depth Decimal | DEP | 259 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |
| Route 2 | DST | 251 | 1 | 27 | 00 | 7f | *Routing Ids* |
| Route 2 Depth | DEP | 260 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 2 Depth Intermediate Step | DEP | 258 | 1 | 00 | 00 | 10 | 00 = 0; 10 = +1 |
| Route 2 Depth Decimal | DEP | 261 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |


#### Routing Ids (Destinations)

| Object | Parameter | Hex |
|-|-|-|
| | None | 60 |
|-|-|-|
| Osc 1 | Pitch Mod | 12 |
| Osc 1 | Freq Mod | 61 |
| Osc 1 | Linear Detune | 02 |
| Osc 1 | Keytrack | 04 |
| Osc 1 | Level | 06 |
| Osc 1 | Waveform | 08 |
| Osc 1 | Sub Oscillator | 0a |
| Osc 1 | Pulse Width | 0c |
| Osc 1 | PWM Speed | 0e |
| Osc 1 | PWM Depth | 10 |
|-|-|-|
| Osc 2 | Pitch Mod | 13 |
| Osc 2 | Freq Mod | 62 |
| Osc 2 | Linear Detune | 03 |
| Osc 2 | Keytrack | 05 |
| Osc 2 | Level | 07 |
| Osc 2 | Waveform | 09 |
| Osc 2 | Sub Oscillator | 0b |
| Osc 2 | Pulse Width | 0d |
| Osc 2 | PWM Speed | 0f |
| Osc 2 | PWM Depth | 11 |
|-|-|-|
| Osc | Osc1+2 Pitch Mod | 14 |
| Osc | Osc1+2 Freq Mod | 63 |
| Osc | Osc1 AM | 18 |
| Osc | Osc1+2 Sync Mode | 1a |
| Osc | Osc1+2 Sync Amount | 1b |
| Osc | Osc1+2 Bend Depth | 1c |
| Osc | Osc1+2 Note Slide Time | 1d |
| Osc | Osc2 AM | 19 |
| Osc | Osc1+2 Vibrato Fade | 1f |
| Osc | Osc1+2 Vibrato Speed | 20 |
| Osc | Osc1+2 Vibrato Depth | 21 |
|-|-|-|
| Noise | Sample and Hold | 15 |
| Noise | Color | 64 |
| Noise | Fade | 16 |
| Noise | Level | 17 |
|-|-|-|
| Amp | EnvA Attack | 35 |
| Amp | EnvA Decay | 38 |
| Amp | EnvA Sustain | 3b |
| Amp | EnvA Release | 3e |
| Amp | EnvA Shape | 41 |
| Amp | Chorus Send | 2d |
| Amp | Delay Send | 2e |
| Amp | Reverb Send | 2f |
| Amp | Pan | 30 |
| Amp | Volume | 31 |
| Amp | Accent Level | 32 |
|-|-|-|
| Env Filter | Attack | 33 |
| Env Filter | Decay | 36 |
| Env Filter | Sustain | 39 |
| Env Filter | Release | 3c |
| Env Filter | Shape | 3f |
| Env Filter | Depth A | 48 |
| Env Filter | Depth B | 49 |
|-|-|-|
| Env User | Attack | 34 |
| Env User | Decay | 37 |
| Env User | Sustain | 3a |
| Env User | Release | 3d |
| Env User | Shape | 40 |
| Env User | Depth A | 4a |
| Env User | Depth B | 4b |
|-|-|-|
| Filter | F1 Frequency | 22 |
| Filter | F1 Resonance | 23 |
| Filter | F1 Overdrive | 24 |
| Filter | F1 EnvF Depth | 26 |
| Filter | F2 Frequency | 27 |
| Filter | F2 Resonance | 28 |
| Filter | F2 EnvF Depth | 2b |
| Filter | F1+F2 Freq | 2c |
|-|-|-|
| Lfo 1 | Speed | 4c |
| Lfo 1 | Multiplier | 4e |
| Lfo 1 | Fade In/Out | 50 |
| Lfo 1 | Start Phase | 52 |
| Lfo 1 | Depth A | 5c |
| Lfo 1 | Depth B | 5d |


#### Letters

| Letter | Hex |
|-|-|
| A | 41 |
| B | 42 |
| C | 43 |
| D | 44 |
| E | 45 |
| F | 46 |
| G | 47 |
| H | 48 |
| I | 49 |
| J | 4a |
| K | 4b |
| L | 4c |
| M | 4d |
| N | 4e |
| O | 4f |
| P | 50 |
| Q | 51 |
| R | 52 |
| S | 53 |
| T | 54 |
| U | 55 |
| V | 56 |
| W | 57 |
| X | 58 |
| Y | 59 |
| Z | 5a |
| + | 2b |
| - | 2d |
| = | 3d |
| & | 26 |
| / | 2f |
| # | 23 |
| @ | 40 |
| ? | 3f |
| % | 25 |
| $ | 24 |
| 0 | 30 |
| 1 | 31 |
| 2 | 32 |
| 3 | 33 |
| 4 | 34 |
| 5 | 35 |
| 6 | 36 |
| 7 | 37 |
| 8 | 38 |
| 9 | 39 |
| ~ | 7e |




