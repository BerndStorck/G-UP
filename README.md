# g-up - Update tool for Debian / Ubuntu

**g-up is a tool that automates the update procedure for Debian based**
**Linux systems like Ubuntu or Linux Lite.**

## License

g-up is free software. You can redistribute it and/or modify it under the
 terms of the GNU General Public License Version 2.0. as published by
 the Free Software Foundation. A copy of the GNU GPL 2.0 is provided with the
software.

## Installation

Unzip the "g-up" bash script from the zip archive and move it to either
 `/usr/local/bin` or `~/bin`. You can either do this from a command line or simply
 drag the file out of Archive Manager to wherever you'd like it to go.

Note: scripts that are run from the `~/bin` directory cannot be prefixed with
 `sudo` as the system will fail to find them. Those who intend to run up from
 a script for cron, anacron or systemd timers should place it in `/usr/local/bin`
 This is also the best practice if there are more than one administrator
 accounts on the machine.

## Command Options


### Run without Options

Running `g-up` with no options will update the apt cache and then perform a full distribution update automatically:
    

```bash
g-up
```

### --clean

Adding the "`--clean`" option will invoke the apt commands to search for and remove locally cached packages that are no longer in the repositories and remove orphaned packages that are no longer needed by programs: 
    

```bash
g-up --clean
```

### --remove 

The `--remove` option only removes orphaned packages, leaving the apt cache alone: 

```bash
g-up --remove
```

### --help

Show the help page:

```bash
g-up --help
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

## History

I developed `g-up` based on versions 1.0 and 1.2 of the bash script `up` by Joe Collins (ezeelinux.com). 

Collins has shown the version 1.0 at the end of his Youtube-Video "A Beginner's Introduction to BASH Shell Scripting" at https://www.youtube.com/watch?v=_n5ZegzieSQ (2018-08-09). Version 1.2 can be downloaded from Github: https://codeload.github.com/EzeeLinux/up-debian_ubuntu_update_tool/zip/master 

Coded by Bernd Storck, https://facebook.com/BStLinux/.

### Differences between g-up and up

`g-up` is nearly a complete reimplementation or at least a total code review and enhancement of `up`.

- Multilanguage support added: Screen messages in German and English.
- Complete change of the main control structure.
- Some attempts to speed up the script al little: One function call removed, slightly code redundancy in favour of speed, reduction of apt-get's screen output.
- Additional option for clean only the Apt-Cache.
- Additional short options `-h` for `--help` and `-c` for `--clean`, `-r` for `--remove`.
- Additional options to request the script's version.
- Bug fix: Wrong check for existense of the pager less removed and replaced by a function, which checks the existense of a known pager.
- Usage of the pager depending on terminal height and text to display. 

## Disclaimer

This software is provided “as is” and any express or implied warranties, including, but not limited to, the implied warranties of merchantability and fitness for a particular purpose are disclaimed. In no event shall the program author be liable for any direct, indirect, incidental, special, exemplary, or consequential damages (including, but not limited to, procurement of substitute goods or services; loss of use, data, or profits; or business interruption) however caused and on any theory of liability, whether in contract, strict liability, or tort (including negligence or otherwise) arising in any way out of the use of this software, even if advised of the possibility of such damage.