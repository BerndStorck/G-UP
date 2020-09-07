# g-up - Update tool for Debian / Ubuntu

**g-up is a tool that automates the update procedure for Debian based**
**Linux systems like Ubuntu or Linux Lite.**

## History

This script was derived from Joe Collins (ezeelinux.com) scripts `up 1.0` and `up 1.2` . 

Collins has shown the version 1.0 at the end of his Youtube-Video "A Beginner's Introduction to BASH Shell Scripting" at https://www.youtube.com/watch?v=_n5ZegzieSQ (2018-08-09). Version 1.2 can be downloaded from Github: https://codeload.github.com/EzeeLinux/up-debian_ubuntu_update_tool/zip/master 

### Differences between g-up and up

`g-up` is nearly a complete reimplementation or at least a total code review and enhancement of `up`.

- Multilanguage support added: Screen messages in German and English.

- Complete change of the main control structure.
- Some attempts to speed up the script al little: One function call removed, slightly code redundancy in favour of speed, reduction of apt-get's screen output.
- Additional option for clean only the Apt-Cache.

- Additional short options `-h` for `--help` and `-c` for `--clean`, `-r` for `--remove`.

- Bug fix: Wrong check for existense of the pager less removed and replaced by a function, which checks the existense of a known pager.
- Usage of the pager depending of terminal height and text to display. 

## Installation

Unzip the "go-up" bash script from the zip archive and move it to either
 `/usr/local/bin` or `~/bin`. You can either do this from a command line or simply
 drag the file out of Archive Manager to wherever you'd like it to go.

Note: scripts that are run from the `~/bin` directory cannot be prefixed with
 `sudo` as the system will fail to find them. Those who intend to run up from
 a script for cron, anacron or systemd timers should place it in `/usr/local/bin`
 This is also the best practice if there are more than one administrator
 accounts on the machine.

## Command Options


### Run without Options
Running `up` with no options will update the apt cache and then perform a full distribution update automatically:
    

```bash
up
```

### --clean

Adding the "`--clean`" option will invoke the apt commands to search for and remove locally cached packages that are no longer in the repositories and remove orphaned packages that are no longer needed by programs: 
    

```bash
up --clean
```

### --remove 

The `--remove` option only removes orphaned packages, leaving the apt cache alone: 

```bash
up --remove
```

### --help

Show the help page:

```bash
up --help
```

### --version

Display version info:

```bash
g-up --version  
```

### -#

Write only the version number:

```bash
g-up -#
```

Disclaimer:

THIS SOFTWARE IS PROVIDED BY EZEELINUX “AS IS” AND ANY EXPRESS OR IMPLIED
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
EVENT SHALL EZEELINUX BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL,
EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR
BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER
IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.
## License

go-up is free software. You can redistribute it and/or modify it under the
 terms of the GNU General Public License Version 2.0. as published by
 the Free Software Foundation. A copy of the GNU GPL 2.0 is provided with the
software.