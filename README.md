# ttd

**T**ime-**T**o-**D**ate — a tiny script that tells you how many days remain until a date.

```sh
ttd 07-22-2026
# 34 days until July 22
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
ttd MM-DD-YYYY    Days until the given date (month-day-year)
ttd -h            Show help
ttd -v            Show version
```

Dates use `MM-DD-YYYY` format:

```sh
ttd 07-22-2026    # days until July 22, 2026
ttd 12-25-2026    # days until December 25, 2026
```

If the date is today, output is `Today is <Month> <Day>`. Past dates report how many days ago.

## License

MIT