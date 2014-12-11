# Packets
## Light
### Light on/off mode
- ID 1111: 0111110000001
- ID 0000: 0100000000001
- ID 0110: 0101100000001
- ID 0101: 0101010000001

### Dim mode
- ID 1111: 0111111000001
- ID 0000: 0100001000001

## Fan reverse
### Light on/off mode
- ID 1111: 0111111000100
- ID 0000: 0100000000100

### Dim mode
- ID 1111: 0111110000100
- ID 0000: 0100001000100

## Fan off
### Light on/off mode
- ID 1111: 0111110000010
- ID 0000: 0100000000010

## Fan speed
### Light on/off mode
#### Speed 1
- ID 1111: 0111110001000
- ID 0000: 0100000001000

#### Speed 2
- ID 1111: 0111110010000
- ID 0000: 0100000010000

#### Speed 3
- ID 1111: 0111110100000
- ID 0000: 0100000100000

# Packet format
`01[ID len: 4][payload len: 7]`

# Payload format

Bit Position | Function of bit when true (1)
-------------|------------------------------
Bit 0        | Light on/off or dim mode
Bit 1        | Set fan speed to 3
Bit 2        | Set fan speed to 2
Bit 3        | Set fan speed to 1
Bit 4        | Reverse fan direction
Bit 5        | Turn fan off
Bit 6        | Toggle or dim light

- Bit 0
  - False (0): Light on/off
  - True (1): Dim mode
  - This also affects the function of bit 6

- Bit 6
  - Toggle light on/off when bit 0 is false, dim light brightness when bit 0 is true.

## Timing
'0' bit: on for 0.0003222 sec followed by off for 0.0003222 sec

'1' bit: on for 0.00071367 sec followed by off for 0.0003222 sec
