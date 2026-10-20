# ratrecon

A lightweight Linux system reconnaissance tool with a rat-themed ASCII art output, inspired by neofetch.

Built as a learning project on the path to penetration testing. Not a replacement for tools like `linpeas`, but a personal utility for quick system overview and a demonstration of Bash scripting skills.

## Features

- System info: kernel, hostname, current user
- Network: primary IP address
- Listening ports count
- Non-system users count
- Cron tasks count
- Running services count
- SUID files (potential privilege escalation vectors)

## Screenshot

![ratrecon screenshot](assets/screenshot.png)

## Example Output

```
               _                       __
              /   \                  /      \
             '      \              /          \
            |       |Oo          o|            |
            `    \  |OOOo......oOO|   /        |
             `    \\OOOOOOOOOOOOOOO\//        /
               \ _o\OOOOOOOOOOOOOOOO//. ___ /
           ______OOOOOOOOOOOOOOOOOOOOOOOo.___
            --- OO'* `OOOOOOOOOO'*  `OOOOO--
                OO.   OOOOOOOOO'    .OOOOO o            nogasobaki@arch-pc
                `OOOooOOOOOOOOOooooOOOOOO'OOOo          -----------------
              .OO "OOOOOOOOOOOOOOOOOOOO"OOOOOOOo        Kernel: 7.2.9-arch1-1
          __ OOOOOO`OOOOOOOOOOOOOOOO"OOOOOOOOOOOOo      Network: 172.19.0.1
         ___OOOOOOOO_"OOOOOOOOOOO"_OOOOOOOOOOOOOOOO     Ports: 10 listening
           OOOOO^OOOO0`(____)/"OOOOOOOOOOOOO^OOOOOO     Users: 1 non-system
           OOOOO OO000/000000\000000OOOOOOOO OOOOOO     Cron: 0 tasks
           OOOOO O0000000000000000 ppppoooooOOOOOO      Services: 25 running
           `OOOOO 0000000000000000 QQQQ "OOOOOOO"       SUID files:
            o"OOOO 000000000000000oooooOOoooooooO'        /usr/lib/virtualbox/VBoxNetAdpCtl
            OOo"OOOO.00000000000000000000OOOOOOOO'        /usr/lib/virtualbox/VBoxSDL
           OOOOOO QQQQ 0000000000000000000OOOOOOO         /usr/lib/virtualbox/VBoxNetDHCP
          OOOOOO00eeee00000000000000000000OOOOOOOO.       /usr/lib/virtualbox/VBoxHeadless
         OOOOOOOO000000000000000000000000OOOOOOOOOO
         OOOOOOOOO00000000000000000000000OOOOOOOOOO
         `OOOOOOOOO000000000000000000000OOOOOOOOOOO
           "OOOOOOOO0000000000000000000OOOOOOOOOOO'
             "OOOOOOO00000000000000000OOOOOOOOOO"
  .ooooOOOOOOOo"OOOOOOO000000000000OOOOOOOOOOO"
.OOO"""""""""".oOOOOOOOOOOOOOOOOOOOOOOOOOOOOo
OOO            QQQQO"'                 `"QQQQ
`OOo.
  `"OOOOOOOOOOOOoooooooo.
```

## Requirements

- Linux
- Bash 4+
- Standard utilities: `ip`, `ss`, `awk`, `find`, `systemctl`

## Installation

```bash
git clone https://github.com/nogasobaki1/ratrecon.git
cd ratrecon
chmod +x ratrecon

# Optional: add to PATH for global access
echo "export PATH=\"\$PATH:$(pwd)\"" >> ~/.bashrc
source ~/.bashrc
```

## Usage

```bash
./ratrecon
```

Or, if added to PATH:

```bash
ratrecon
```

## How it works

The script reads ASCII art from `assets/logo.txt` into an array, builds the system information array, then prints both side by side with vertical centering.

## Motivation

I am building this project as part of my learning path toward penetration testing. I wanted to create my own project, so I developed a tool that displays system information in a clean and readable format. The rat theme was not chosen by chance: a rat sniffs out and gathers information - that is, it conducts reconnaissance.

## Notes

- SUID scan runs on the entire filesystem, so first launch may take 10–30 seconds.
- For full port and service details, run with `sudo`.
- Tested on Arch Linux and Kali Linux.

## Roadmap

- [ ] Add `--help` flag
- [ ] Export report to file (`--output report.txt`)
- [ ] Parallel SUID scan for speed

## License

MIT - see [LICENSE](LICENSE)

## Author

**nogasobaki1** - [GitHub](https://github.com/nogasobaki1)

---

*This tool is intended for educational and authorized testing purposes only.*

---

[Русская версия / Russian version](README.ru.md)
