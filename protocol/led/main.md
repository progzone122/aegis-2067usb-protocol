# LED Settings
Configuration of animation effect, brightness, speed of backlight animation

## Setup Data
| Parameter | Value  |
|-----------|--------|
| wValue    | 0x0307 |
| wIndex    | 1      |
| wLength   | 8      |

## Data fragment

### HEX dump example
```hexdump
07 ff ff 07 05 01 00 00
```

### Details

| # | Value(s) | Description                                |
|---|----------|--------------------------------------------|
| 0 | 0x07     |                                            |
| 1 | 0xff     |                                            |
| 2 | 0xff     |                                            |
| 3 | ?        | [Animation effect](./animation_effects.md) |
| 4 | ?        | [LED Brightness](./led_brightness.md)      |
| 5 | ?        | [Animation speed](./animation_speed.md)    |
| 6 | ?        | [Loader](./loader.md)                      |
| 7 | 0x00     |                                            |

[?] - can have many different meanings

