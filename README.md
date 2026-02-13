# FlipCode VM

esolang with 1M+ transistors. runs in browser.

## commands

only three:
- `flip N` - toggle transistor N (0-1048575)
- `clock N` - do N clock cycles, output ASCII from T0-T7 each tick
- `end` - stop
- `# blah` - comment

## how it works

transistors 0-7 form an 8-bit register. when you `clock`, it reads these as ASCII:
- T0 = bit 0 (LSB)
- T1 = bit 1
- T2 = bit 2
- etc

example: to output 'H' (72 = 0b01001000):
```
flip 3
flip 6
clock 1
```

## hello world

see hello_world.flip. flip transistors to build each character, remembering that flip TOGGLES the state.

## tech stuff

- 1,048,576 total transistors
- sparse storage (Map) - only stores active ones
- no dependencies
- single html file

## deploy

works locally or on vercel:
```
vercel
```
