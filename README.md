This is a fork of https://github.com/technomancy/tmk_keyboard

This is README is for people how are bored to look for doc everywhere. I have an atreus with PCB soldered in the wrong side so to build I need to use `PCBDOWN` (more infos below).

1. Get dependencies: Install `gcc-avr` and `avrdude`
2. `$ cd keyboard/atreus`
3. Check `keymap_ergodox_style.c` for how the keycaps are implemented.
4. Which is your usb input? For that run `ls /dev` with the keyboard not plug then plug it and run reset mode.

To run reset mode go on layer 2 with `fn + esc` then press `reset`.

```
 insert home    ↑    end  pgup     ||       ↑     F7    F8    F9   F10
   del   ←      ↓     →   pgdn     ||       ↓     F4    F5    F6   F11
                          reset    ||             F1    F2    F3   F12
             super shift bksp ctrl || alt space   L0
```

You should be able to see the keyboard after 1-2 sec. On my mac it is `/dev/tty.usbmodem1411`

5. And because my PCB is up side down `OPT_DEFS=-DPCBDOWN make upload KEYMAP=ergodox_style USB=/dev/tty.usbmodem1411`

