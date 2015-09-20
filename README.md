# README #

Update to lcdproc i2c to allow the pin configurations to be specified via LCDd.conf.

# alternative wiring example #


```

   PCF8574AP: P0 P1 P2 P3 P4 P5 P6 P7
              |  |  |  |  |  |  |  |
   HD44780:   RS RW EN BL D4 D5 D6 D7

```

LCDd.conf

```
## Hitachi HD44780 driver ##
[HD44780]
ConnectionType=i2c
Device=/dev/i2c-1
Port=0x27
Backlight=yes
Size=20x4
DelayBus=false
DelayMult=1
Keypad=no
Speed=0
i2c_line_RS=0x01
i2c_line_RW=0x02
i2c_line_EN=0x04
i2c_line_BL=0x80
i2c_line_D4=0x10
i2c_line_D5=0x20
i2c_line_D6=0x40
i2c_line_D7=0x80
Backlight=yes
BacklightInvert=yes
```

The Backlight Invert is used if a 0 turns the backlight on, and 1 turns it off, i.e. npn
 transistor

See discussion here:
http://sourceforge.net/p/lcdproc/discussion/312/thread/00298b2f/


Added compiled hd44780.so - save to:
/usr/lib/lcdproc/hd44780.so
