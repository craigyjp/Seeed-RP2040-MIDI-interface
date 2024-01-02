# Seeed-RP2040-MIDI-interface

This is taken from the MIDI pico adaptor by Rene Stange and modified to run on a Seeed RP2040 and the makefile updated to compile with the latest Pico-SDK and Visual Studio.

https://github.com/rsta2/pico/tree/main/midi_adapter

This program is a USB to serial MIDI adapter. It connects to an USB host via the
USB connector of the Seeed RP2040 on one side and to a MIDI device with
serial interface via GP0 (UART TX)/GP1 (RX) on the other side. MIDI
messages/events, received on one side, will be converted and send out on the
other side. The LED on the RP2040 board flashes, when MIDI data is
exchanged.

This unit can be used as a connection to a Raspberry PI which can only provide USB Host connections. 
Connecting this device to a Pi will give you standard DIN midi input and putput

The Seeed RP2040 is powered via USB, the VSYS or VBUS pins must NOT be
connected!

The MIDI adapter receives USB MIDI events from all virtual MIDI cables, and it
sends USB MIDI data to the virtual MIDI cable zero.

If you enable the #define IGNORE_MIDI_CC in the file main.c, the MIDI control
change and program change events, which have be received from the USB host, will
be filtered out and ignored.
