# ostrich2
Command line interface for [Ostrich 2.0](http://support.moates.net/2008/09/11/ostrich-20-overview/), an EPROM emulator.

## Requirements

### Windows
- install [FTDI virtual COM port drivers](http://www.ftdichip.com/Drivers/VCP.htm)
- install [Python 3](http://www.python.org/download/releases/3.2.3/) and [pyserial](http://www.lfd.uci.edu/~gohlke/pythonlibs/#pyserial)

### Mac OS X

- install [FTDI virtual COM port drivers](http://www.ftdichip.com/Drivers/VCP.htm)
- install Python 3 and `pyserial`

e.g. using [MacPorts](http://www.macports.org/):

    sudo port install python32 py32-serial

### Linux
- install Python 3 and `pyserial`

e.g. using `apt-get`:

    sudo apt-get install python3 python3-serial

---

## Usage

Pass the `--help` parameter to get brief usage instructions:

    ostrich2.py --help

### Read memory
Get a binary dump of memory.

    ostrich2.py read 0x0000 0x1fff > 2k-dump.bin

### Write memory
Write data to memory.

    ostrich2.py write --address 0x0000 < 2k-dump.bin

### Check device version info

    ostrich2.py version

---

## Serial ports

Ostrich 2.0 uses a (virtual) serial port for communication. The program will try to guess the name of the port, but may get confused if there are other FTDI devices connected (e.g. Arduino).
If you're having problems connecting to the device you may have to explicitly declare which port to use:

    ostrich2.py --device COM4 ...
