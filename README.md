## frinkconv

A wrapper script for interacting with the [Frink language](https://frinklang.org/), with a focus on converting units

I've tried many CLI unit conversion tools/systems, and so far, have found Frink the best.

However, using it from the CLI can be a bit tedious, so this:

- Handles downloading the JAR/data files
- Wraps frink in `rlwrap` to provide symbol auto completion (can hit `tab` to complete unit names) and history support
- Provides 2 interfaces:
  - The default REPL
  - A non-interactive expression mode, which executes anything passed as command line arguments

For the list of supported units, see [here](https://frinklang.org/frinkdata/units.txt)

This was converted to modern `bash` and made configurable from the ['starter script'](https://frinklang.org/frinkjar/frink)

## Install

Requires: `java`, `rlwrap`, `wget`

Copy the `frinkconv` script onto your `$PATH` and make it executable

Could use [`basher`](https://github.com/basherpm/basher) to do that for you:

```bash
basher install seanbreckenridge/frinkconv
```

## Examples

Interactive mode:

```
$ frinkconv
Dropping into repl...
Frink - Copyright 2000-2021 Alan Eliasen, eliasen@mindspring.com.
10 hours -> sec
36000
200 gigabytes -> kilobytes
200000000
1 lunarmonth -> solardays
29.5305555
20 gallons -> fluidounces
2560
1 kilometer -> mile
15625/25146 (approx. 0.62137119223733397)
```

Expression mode:

```
$ frinkconv '19328 seconds -> minutes'
4832/15 (approx. 322.13333333333333)
```
