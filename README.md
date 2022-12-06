# plotGNU

> Plot data files that might not play nicely with plotting software due to columns of different lengths or missing data points.

**plotGNU** uses `gnuplot` to plot data files, which could be missing data points.
Column separators should be at least one empty space.

## Installation / uninstallation

The following additional variables are supported:
- `DESTDIR` -- determines environment for staged installs,
- `PREFIX`  -- determines the value of `BINDIR`              (default: `$${HOME}/.local`).
- `BINDIR`  -- determines where the script will be installed (default: `$(PREFIX)/bin`).

To **install**, just run `make`.\
To **uninstall**, just run `make uninstall`.

To change the value of any `make` variables, run, e.g., `make FOO=bar install`

## Requirements

The script requires the following to run:
- `gnuplot`
- `linux`

## Usage

Run: `plotGNU [options] [file(s)_to_plot]`

| Operation                | Description                                                  |
| :------------------------| :------------------------------------------------------------|
| `-h`                     | Show this message.                                           |
| `-v`                     | Increase verbosity. Might be helpful for debugging.          |
| `-o,--opt STR`           | Pass string STR to the gnuplot plot command.                 |
| `-p,--pre STR`           | Pass string STR to gnuplot before the plot command. <br> Individual commands should be delimited by a semicolon, `;`. |

e.g.,

`plotGNU -v --pre "set logscale xy; set yrange [1:10]" --opt "notitle w lp lt 1 lc 3 ps 4 pt 1" datafile(s)_to_plot`
