# Elektron A4 Sound SysEx

OS Version: OS 1.40A

**INFO:** Apparently the patch size has change from 415 to 413 Bytes. Byte 2 + 3 have been removed.


#### Meta

* Header -> 0-21 -> 22 Bytes
* Name -> 22-38 -> 17 Bytes (24 = 0x00; 32 = 0x00)


## Parameters

#### Header

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Program Number | | 07 | 1 | 00 | 00 | ff | 256 Sounds |
| Tags | | 16 | 1 | 00 | 00 | 3c | 4 [Tags](#tags) (bit field) |
| Tags | | 18 | 1 | 00 | 00 | 7f | 7 [Tags](#tags) (bit field) |
| Tags | | 19 | 1 | 00 | 00 | 7f | 7 [Tags](#tags) (bit field) |
| Tags | | 20 | 1 | 00 | 00 | 7f | 7 [Tags](#tags) (bit field) |
| Tags | | 21 | 1 | 00 | 00 | 7f | 7 [Tags](#tags) (bit field) |


#### Footer

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Checksum | | 408 | 2 | 00 00 | 00 00 | 7f 7f | Sum of all Bytes from 08 to 407 |
| File Size | | 410 | 2 | 03 15 | 03 15 | 03 15 | Fixed length of 413 Bytes |
| End Marker | | 412 | 1 | 7f | 7f | 7f | Last Byte |


#### OSC1

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Coarse Tune | TUN | 41 | 1 | 40 | 00 | 7f | -63 to +63 |
| Fine Tune | FIN | 42 | 1 | 00 | 00 | 7f | -64 to -1 and 0 to +63 (02 = +1, 05 = +2, ..., 7f = 63; 7f = -1, 7d = -2, ..., 00 = -64) |
| Fine Tune +/- | FIN | 40 | 1 | 00 | 00 | 20 | 20 = -Range; 00 = +Range |
| Detune | DET | 45 | 1 | 40 | 00 | 7f | -64 to +63 |
| Keytrack | TRK | 50 | 1 | 01 | 00 | 01 | Off/On |
| Level | LEV | 54 | 1 | 64 | 00 | 7f | 0 to 127 |
| Wave Shape | WAV | 59 | 1 | 00 | 00 | 07 | 8 [Wave Shapes](#wave-shapes) |
| Sub Oscillator | SUB | 63 | 1 | 00 | 00 | 04 | 5 [Sub Oscillators](#sub-oscillators) |
| Pulse Width | PW | 68 | 1 | 40 | 00 | 7f | -64 to +63 |
| PWM Speed | SPD | 73 | 1 | 0a | 00 | 7f | 0 to 127 |
| PWM Depth | PWM | 77 | 1 | 00 | 00 | 7f | 0 to 127 |
| Amplitude Modulation | AM1 | 95 | 1 | 00 | 00 | 01 | Off/On |


#### NOISE

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Sample & Hold | SNH | 89 | 1 | 00 | 00 | 7f | 0 to 127 |
| Color | COL | 269 | 1 | 40 | 00 | 7f | -64 to +63 |
| Fade | FAD | 91 | 1 | 40 | 00 | 7f | -64 to +63 |
| Level | LEV | 93 | 1 | 00 | 00 | 7f | 0 to 127 |


#### OSC2

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Coarse Tune | TUN | 43 | 1 | 40 | 00 | 7f | -63 to +63 |
| Fine Tune | FIN | 44 | 1 | 00 | 00 | 7f | -64 to -1 and 0 to +63 (02 = +1, 05 = +2, ..., 7f = 63; 7f = -1, 7d = -2, ..., 00 = -64) |
| Fine Tune +/- | FIN | 40 | 1 | 00 | 00 | 08 | 08 = -Range; 00 = +Range |
| Detune | DET | 47 | 1 | 40 | 00 | 7f | -64 to +63 |
| Keytrack | TRK | 52 | 1 | 01 | 00 | 01 | Off/On |
| Level | LEV | 57 | 1 | 00 | 00 | 7f | 0 to 127 |
| Wave Shape | WAV | 61 | 1 | 00 | 00 | 07 | 8 [Wave Shapes](#wave-shapes) |
| Sub Oscillator | SUB | 66 | 1 | 00 | 00 | 04 | 5 [Sub Oscillators](#sub-oscillators) |
| Pulse Width | PW | 70 | 1 | 40 | 00 | 7f | -64 to +63 |
| PWM Speed | SPD | 75 | 1 | 25 | 00 | 7f | 0 to 127 |
| PWM Depth | PWM | 79 | 1 | 00 | 00 | 7f | 0 to 127 |
| Amplitude Modulation | AM2 | 98 | 1 | 00 | 00 | 01 | Off/On |


#### VIBRATO

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Speed | SPD | 114 | 1 | 20 | 00 | 7f | 0 to 127 |
| Depth | VIB | 116 | 1 | 00 | 00 | 7f | 0 to 127 |
| Fade | FAD | 111 | 1 | 40 | 00 | 7f | -64 to +63 |
| Bend Depth | BND | 105 | 1 | 40 | 00 | 7f | -64 to +63 |


#### SLIDE

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Slide Time | SLI | 107 | 1 | 20 | 00 | 7f | 0 to 127 |
| Legato Mode | | 281 | 1 | 00 | 00 | 01 | Off/On (Sound Menu) |
| Portamento | | 279 | 1 | 02 | 00 | 02 | Off/On/Legato (Sound Menu) |


#### SYNC

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Sync Amount | SNC | 102 | 1 | 7f | 00 | 7f | 0 to 127 |
| OSC Retrig | TRG | 109 | 1 | 00 | 00 | 01 | Off/On |
| OSC Drift | | 278 | 1 | 01 | 00 | 01 | Off/On (Sound Menu) |
| Mode | SMD | 100 | 1 | 00 | 00 | 03 | Off/1->2/2->1/Metal |


#### Low-Pass-Filter

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Frequency | FRQ | 118 | 2 | 7f 00 | 00 00 | 7f 00 | 0.0 to 127.0; 0.10 = floor(10*2.56) = 19 |
| Freq Decimal Factor | FRQ | 112 | 1 | 00 | 00 | 01 | 0.00-0.49 = 00; 0.50-0.99 = 01 |
| Resonance | RES | 121 | 1 | 14 | 00 | 7f | 0 to 127 |
| Overdrive | OVR | 123 | 1 | 40 | 00 | 7f | -64 to +63 |
| Keytrack | TRK | 125 | 1 | 40 | 00 | 7f | -64 to +63 |
| Envelope Depth | DEP | 127 | 1 | 40 | 00 | 7f | -64 to +63 |
| F1 Resonance Boost | | 283 | 1 | 01 | 00 | 01 | Off/On |


#### Multi-Mode-Filter

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Frequency | FRQ | 130 | 2 | 00 00 | 00 00 | 7f 00 | 0.0 to 127.0; 0.22 = floor(22*2.56) = 0x38 |
| Freq Decimal Factor | FRQ | 128 | 1 | 00 | 00 | 10 | 0.00-0.49 = 00; 0.50-0.99 = 10 |
| Resonance | RES | 132 | 1 | 0c | 00 | 7f | 0 to 127 |
| Type | TYP | 134 | 1 | 04 | 00 | 06 | 7 [Filter Types](#filter-types) |
| Keytrack | TRK | 137 | 1 | 40 | 00 | 7f | -64 to +63 |
| Envelope Depth | DEP | 139 | 1 | 40 | 00 | 7f | -64 to +63 |


#### AMP (Envelope)

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Attack | ATK | 162 | 1 | 00 | 00 | 7f | 0 to 127 |
| Decay | DEC | 169 | 1 | 40 | 00 | 7f | 0 to 127 |
| Sustain | SUS | 175 | 1 | 64 | 00 | 7f | 0 to 127 |
| Release | REL | 182 | 1 | 08 | 00 | 7f | 0 to 127 (127 = Infinite) |
| Shape | SHP | 189 | 1 | 02 | 00 | 0b | 12 [Envelope Shapes](#envelope-shapes) (01 = 00 + Restart etc.) |
| Chorus | CHO | 143 | 1 | 00 | 00 | 7f | 0 to 127 |
| Delay | DEL | 146 | 1 | 00 | 00 | 7f | 0 to 127 |
| Reverb | REV | 148 | 1 | 00 | 00 | 7f | 0 to 127 |
| Pan | PAN | 150 | 1 | 40 | 00 | 7f | L64 to R63 |
| Amp Level | VOL | 153 | 1 | 64 | 00 | 7f | 0 to 127 |


#### Envelope (Filter)

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Shape | SHP | 185 | 1 | 02 | 00 | 0b | 12 [Envelope Shapes](#envelope-shapes) (01 = 00 + Restart etc.) |
| Attack | ATK | 157 | 1 | 00 | 00 | 7f | 0 to 127 |
| Decay | DEC | 164 | 1 | 40 | 00 | 7f | 0 to 127 |
| Sustain | SUS | 171 | 1 | 40 | 00 | 7f | 0 to 127 |
| Release | REL | 178 | 1 | 08 | 00 | 7f | 0 to 127 (127 = Infinite) |
| Gate Length | LEN | 191 | 1 | 00 | 00 | 7f | Off, 0 to 128 (Exponential) |
| Route 1 | DST | 196 | 1 | 0c | 00 | 7f | [Routing Destinations](#routing-destinations) |
| Route 1 Depth | DEP | 205 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 1 Depth Intermediate Step | DEP | 200 | 1 | 00 | 00 | 02 | 00 = 0; 02 = +1 |
| Route 1 Depth Decimal | DEP | 206 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |
| Route 2 | DST | 198 | 1 | 0d | 00 | 7f | [Routing Destinations](#routing-destinations) |
| Route 2 Depth | DEP | 207 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 2 Depth Intermediate Step | DEP | 208 | 1 | 00 | 00 | 40 | 00 = 0; 40 = +1 |
| Route 2 Depth Decimal | DEP | 209 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |


#### Envelope 2 (User)

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Shape | SHP | 187 | 1 | 02 | 00 | 0b | 12 [Envelope Shapes](#envelope-shapes) (01 = 00 + Restart etc.) |
| Attack | ATK | 159 | 1 | 00 | 00 | 7f | 0 to 127 |
| Decay | DEC | 166 | 1 | 40 | 00 | 7f | 0 to 127 |
| Sustain | SUS | 173 | 1 | 40 | 00 | 7f | 0 to 127 |
| Release | REL | 180 | 1 | 08 | 00 | 7f | 0 to 127 (127 = Infinite) |
| Gate Length | LEN | 194 | 1 | 00 | 00 | 7f | Off, 0 to 128 (Exponential) |
| Route 1 | DST | 201 | 1 | 4c | 00 | 7f | [Routing Destinations](#routing-destinations) |
| Route 1 Depth | DEP | 210 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 1 Depth Intermediate Step | DEP | 208 | 1 | 00 | 00 | 10 | 00 = 0; 10 = +1 |
| Route 1 Depth Decimal | DEP | 211 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |
| Route 2 | DST | 203 | 1 | 0d | 00 | 7f | [Routing Destinations](#routing-destinations) |
| Route 2 Depth | DEP | 212 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 2 Depth Intermediate Step | DEP | 208 | 1 | 00 | 00 | 04 | 00 = 0; 04 = +1 |
| Route 2 Depth Decimal | DEP | 213 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |


#### LFO 1

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Shape | SHP | 237 | 1 | 00 | 00 | 06 | 7 [LFO Shapes](#lfo-shapes) |
| Mode | MOD | 233 | 1 | 00 | 00 | 04 | 5 [LFO Modes](#lfo-modes) |
| Start Phase | SPH | 228 | 1 | 00 | 00 | 7f | 0 to 127 |
| Fade | FAD | 223 | 1 | 40 | 00 | 7f | 0 to 127 |
| Speed | SPD | 214 | 1 | 70 | 00 | 7f | 0 to 127 |
| Multiplier | MUL | 219 | 1 | 04 | 00 | 23 | 3 x 12 [LFO Multipliers](#lfo-multipliers) |
| Route 1 | DST | 242 | 1 | 22 | 00 | 7f | [Routing Destinations](#routing-destinations) |
| Route 1 Depth | DEP | 251 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 1 Depth Intermediate Step | DEP | 248 | 1 | 00 | 00 | 08 | 00 = 0; 08 = +1 |
| Route 1 Depth Decimal | DEP | 252 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |
| Route 2 | DST | 244 | 1 | 27 | 00 | 7f | [Routing Destinations](#routing-destinations) |
| Route 2 Depth | DEP | 253 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 2 Depth Intermediate Step | DEP | 248 | 1 | 00 | 00 | 02 | 00 = 0; 02 = +1 |
| Route 2 Depth Decimal | DEP | 254 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |


#### LFO 2

| Parameter | Short | Addr | Len | Def | Min | Max | Comment |
|-|-|-|-|-|-|-|-|
| Shape | SHP | 239 | 1 | 00 | 00 | 06 | 7 [LFO Shapes](#lfo-shapes) |
| Mode | MOD | 235 | 1 | 00 | 00 | 04 | 5 [LFO Modes](#lfo-modes) |
| Start Phase | SPH | 230 | 1 | 00 | 00 | 7f | 0 to 127 |
| Fade | FAD | 226 | 1 | 40 | 00 | 7f | 0 to 127 |
| Speed | SPD | 217 | 1 | 60 | 00 | 7f | 0 to 127 |
| Multiplier | MUL | 221 | 1 | 04 | 00 | 23 | 3 x 12 [LFO Multipliers](#lfo-multipliers) |
| Route 1 | DST | 246 | 1 | 22 | 00 | 7f | [Routing Destinations](#routing-destinations) |
| Route 1 Depth | DEP | 255 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 1 Depth Intermediate Step | DEP | 256 | 1 | 00 | 00 | 40 | 00 = 0; 40 = +1 |
| Route 1 Depth Decimal | DEP | 257 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |
| Route 2 | DST | 249 | 1 | 27 | 00 | 7f | [Routing Destinations](#routing-destinations) |
| Route 2 Depth | DEP | 258 | 1 | 40 | 00 | 7f | -128 to +127 |
| Route 2 Depth Intermediate Step | DEP | 256 | 1 | 00 | 00 | 10 | 00 = 0; 10 = +1 |
| Route 2 Depth Decimal | DEP | 259 | 1 | 00 | 00 | 7e | 0.00 to 0.99 |


## Options

#### Wave Shapes

| Parameter | Hex |
|-|-|
| SAW | 00 |
| TRP | 01 |
| PUL | 02 |
| TRI | 03 |
| INL | 04 |
| INR | 05 |
| FDB/NEI | 06 |
| OFF | 07 |


#### Sub Oscillators

| Parameter | Hex |
|-|-|
| OFF | 00 |
| 10CT | 01 |
| 20CT | 02 |
| 2PUL | 03 |
| 5TH | 04 |


#### Filter Types

| Parameter | Hex |
|-|-|
| LP2 | 00 |
| LP1 | 01 |
| BP | 02 |
| HP1 | 03 |
| HP2 | 04 |
| BS | 05 |
| PK | 06 |


#### Envelope Shapes

| Parameter | Hex |
|-|-|
| 0 | 00 |
| 1 | 01 |
| 2 | 02 |
| 3 | 03 |
| 4 | 04 |
| 5 | 05 |
| 6 | 06 |
| 7 | 07 |
| 8 | 08 |
| 9 | 09 |
| 10 | 0a |
| 11 | 0b |


#### LFO Shapes

| Parameter | Hex |
|-|-|
| TRI | 00 |
| SIN | 01 |
| SQR | 02 |
| SAW | 03 |
| EXP | 04 |
| RMP | 05 |
| RND | 06 |


#### LFO Multipliers

| Parameter | Hex |
|-|-|
| x1 | 00 |
| x2 | 01 |
| x4 | 02 |
| x8 | 03 |
| x16 | 04 |
| x32 | 05 |
| x64 | 06 |
| x128 | 07 |
| x256 | 08 |
| x512 | 09 |
| x1k | 0a |
| x2k | 0b |
| ·1 | 0c |
| ·2 | 0d |
| ·4 | 0e |
| ·8 | 0f |
| ·16 | 10 |
| ·32 | 11 |
| ·64 | 12 |
| ·128 | 13 |
| ·256 | 14 |
| ·512 | 15 |
| ·1k | 16 |
| ·2k | 17 |
| µ1 | 18 |
| µ2 | 19 |
| µ4 | 1a |
| µ8 | 1b |
| µ16 | 1c |
| µ32 | 1d |
| µ64 | 1e |
| µ128 | 1f |
| µ256 | 20 |
| µ512 | 21 |
| µ1k | 22 |
| µ2k | 23 |


#### LFO Modes

| Parameter | Hex |
|-|-|
| FREE | 00 |
| TRIG | 01 |
| HOLD | 02 |
| ONE | 03 |
| HALF | 04 |


#### Routing Destinations

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


#### Tags

| Tag | Hex | Comment |
|-|-|-|
| Bass | 01 | Byte 21 |
| Lead | 02 | Byte 21 |
| Pad | 04 | Byte 21 |
| Texture | 08 | Byte 21 |
| Chord | 10 | Byte 21 |
| Keys | 20 | Byte 21 |
| Brass | 40 | Byte 21 |
| Strings | 04 | Byte 16 |
| Transient | 01 | Byte 20 |
| Sound FX | 02 | Byte 20 |
| Kick | 04 | Byte 20 |
| Snare | 08 | Byte 20 |
| Hihat | 10 | Byte 20 |
| Percussion | 20 | Byte 20 |
| Atmosphere | 40 | Byte 20 |
| Evolving | 08 | Byte 16 |
| Noisy | 01 | Byte 19 |
| Glitch | 02 | Byte 19 |
| Hard | 04 | Byte 19 |
| Soft | 08 | Byte 19 |
| Expressive | 10 | Byte 19 |
| Deep | 20 | Byte 19 |
| Dark | 40 | Byte 19 |
| Bright | 10 | Byte 16 |
| Vintage | 01 | Byte 18 |
| Acid | 02 | Byte 18 |
| Epic | 04 | Byte 18 |
| Fail | 08 | Byte 18 |
| Tempo Sync | 10 | Byte 18 |
| Input | 20 | Byte 18 |
| Mine | 40 | Byte 18 |
| Favourite | 20 | Byte 16 |


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
