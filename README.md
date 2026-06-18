# ttd

**T**ime-**T**o-**D**ate — a tiny script that tells you how many days remain until a date.

```sh
ttd 07-22-2026
# 33 days until July 22

ttd -a fold8 07-22-2026
# July 22nd, 2026 saved as fold8

ttd fold8
# 33 days until July 22
```

Zero dependencies beyond Bash and GNU `date`.

## Install

```sh
curl -Lo ~/.local/bin/ttd https://raw.githubusercontent.com/Arrowstorm-Technologies-LLC/ttd/main/ttd
chmod +x ~/.local/bin/ttd
```

Make sure `~/.local/bin` is in your PATH:

```sh
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc  # or ~/.zshrc
```

## Usage

```
ttd MM-DD-YYYY         Days until the given date (month-day-year)
ttd <alias>            Days until a saved date alias
ttd -a <alias> <date>  Save a date alias
ttd -h                 Show help
ttd -v                 Show version
```

Dates use `MM-DD-YYYY` format:

```sh
ttd 07-22-2026              # days until July 22, 2026
ttd 12-25-2026              # days until December 25, 2026
ttd -a fold8 07-22-2026     # save July 22, 2026 as "fold8"
ttd fold8                   # days until the saved date
```

Aliases are stored in `~/.config/ttd/aliases`.

If the date is today, output is `Today is <Month> <Day>`. Past dates report how many days ago.

## License

MIT