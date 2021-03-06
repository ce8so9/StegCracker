# StegCracker
[![Build Status](https://travis-ci.org/Paradoxis/StegCracker.svg?branch=master)](https://travis-ci.org/Paradoxis/StegCracker)
[![PyPI version](https://badge.fury.io/py/stegcracker.svg)](https://badge.fury.io/py/stegcracker)
[![codecov](https://codecov.io/gh/Paradoxis/StegCracker/branch/master/graph/badge.svg)](https://codecov.io/gh/Paradoxis/StegCracker)

Steganography brute-force utility to uncover hidden data inside files.

## Usage
Using stegcracker is simple, pass a file to it as it's first parameter and 
optionally pass the path to a wordlist of passwords to try as it's second 
parameter. If you don't specify the wordlist, the tool will try to use the 
built-in rockyou.txt wordlist which ships with Kali Linux. If you are running a 
different distribution, you can download the rockyou wordlist 
[here](https://github.com/danielmiessler/SecLists/raw/master/Passwords/Leaked-Databases/rockyou.txt.tar.gz).

```
$ stegcracker <file> [<wordlist>]
```

## Requirements
The program requires the steghide binary, and Python 3.6 or higher to be installed. If 
python 3.6 is not installed, check out [this](https://unix.stackexchange.com/questions/332641/how-to-install-python-3-6)
guide on how to do so. Steghide can be installed by using the following command (Kali Linux):

```
$ sudo apt-get install steghide -y
```

## Installation
To install StegCracker, run the following command:

```
$ pip3 install stegcracker
```

## Updating
To update StegCracker, simply pass `-U` to the installation command:

```
$ pip3 install stegcracker -U --force-reinstall
```

## Example

![demo](https://github.com/Paradoxis/StegCracker/raw/master/stegcracker.gif)
 
## FAQ / Troubleshooting

* I can't install the tool with `pip3`, but python 3.6+ is installed
    * Your pip binary might be using a different version of Python. Try installing it 
      directly through Python like so (replace "X" with your minor version, eg: `python3.6`): 
      `python3.X -m pip install -U stegcracker`
      
* I installed the tool, but when I run `stegcracker` it just returns 'command not found'
    * Chances are your Python's `bin` directory is not in your PATH envrionment variable. 
      As a dirty fix you could add the following to your `~/.bashrc` file: `alias stegcracker='python3 -m stegcracker'`

* I'm using StegCracker 1.X, how do I upgrade?
    * If you're upgrading StegCracker from the original 1.X release, please 
      remove the existing version first using: `sudo rm --force $(which stegcracker)`

* I want to run an older version of StegCracker, how do I obtain a copy?
    * While I recommended using the latest and greatest version, you might want 
      to install an older version of StegCracker. You can do this
      by checking out the [releases](https://github.com/Paradoxis/StegCracker/releases) 
      page. _(Note: all issues or pull requests regarding this version will be be ignored)_.

* Can I run this tool on other Linux distro's? 
    * As long as you have a valid version of Python 3.6 and steghide in your path
      it *should* work. Please note that the tool has officially been tested on 
      Kali Linux, all other platforms might be unstable. If you find a bug on 
      another distro, please submit an issue and I'll see what I can do 
      _(but do fill in the template as well)_.
      
* Can I run StegCracker on Windows?
    * As far as I know there aren't any official steghide releases for Windows, 
    so as far as I'm aware: no

## License
Copyright 2019 - Luke Paris (Paradoxis)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, 
including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to 
do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND 
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF 
OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
