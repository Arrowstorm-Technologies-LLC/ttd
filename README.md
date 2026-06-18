# ttd

**T**ime-**T**o-**D**ate — a tiny script that tells you how many days remain until a date.

Pass a date and get a plain answer. Save short aliases for dates you check often — deadlines, launches, holidays — and look them up by name instead of remembering `MM-DD-YYYY`.

Zero dependencies. One Bash script. No build step.

```
ttd 07-22-2026              # days until July 22
ttd -a fold8 07-22-2026     # save that date as "fold8"
ttd fold8                   # days until the saved date
```

## Install

```sh
curl -Lo ~/.local/bin/ttd https://raw.githubusercontent.com/Arrowstorm-Technologies-LLC/ttd/main/ttd
chmod +x ~/.local/bin/ttd
```

Make sure `~/.local/bin` is in your PATH:

```sh
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.bashrc  # or ~/.zshrc
```

Or install via [rack](https://github.com/Arrowstorm-Technologies-LLC/rack):

```sh
rack ttd Arrowstorm-Technologies-LLC/ttd
```

## Usage

```
ttd MM-DD-YYYY         Days until the given date
ttd <alias>            Days until a saved date alias
ttd -a <alias> <date>  Save a date alias
ttd -h                 Show help
ttd -v                 Show version
```

### Count down to a date

Dates use `MM-DD-YYYY` format:

```sh
ttd 07-22-2026
# 33 days until July 22

ttd 12-25-2026
# 190 days until December 25
```

### Save and use aliases

Give a memorable name to any date:

```sh
ttd -a fold8 07-22-2026
# July 22nd, 2026 saved as fold8

ttd fold8
# 33 days until July 22
```

Saving again with the same alias overwrites the previous date. Aliases must start with a letter and may contain letters, numbers, `_`, and `-`.

Aliases are stored in `~/.config/ttd/aliases` as `alias=MM-DD-YYYY`.

### Output

- **Future dates:** `33 days until July 22`
- **Today:** `Today is June 18`
- **Past dates:** `5 days ago (June 13)`
- Singular `day` is used when the count is 1.

## How it works

1. Parses the input as `MM-DD-YYYY`, or resolves a saved alias to a date.
2. Compares the target date to today using GNU `date` epoch seconds.
3. Prints the day count with a friendly month and day label.

## Requirements

- Bash 4+
- GNU `date` (standard on Linux)

## License

MIT — see [LICENSE](LICENSE).