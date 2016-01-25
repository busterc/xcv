# xcv

Cut, Copy and Paste files with Bash

```sh
$ xcv
Usage: $ xcv <x|c|v|l> [options]

  Description:
    xcv wraps the cp, mv and ls built in commands, however
    cutting (x) and copying (c) do not require a target directory, while
    pasting (v) and listing (l) do not require a source directory, because all selected
    files are placed into, listed and pulled from:
    $HOME/.xcv

  Options:
    x  Cut files, using the mv command options
    c  Copy files, using the cp command options
    v  Paste files into the current working directory
    l  List files available for pasting, using the ls command options
```

## Homebrew Installation

```sh
$ brew install xcv
```

## Bpkg Installation

With [bpkg](https://github.com/bpkg/bpkg) do:

```sh
$ bpkg install busterc/xcv
```

## NPM Installation

```sh
$ npm install xcv --global
```

## Nifty Aliases

```sh
alias fsx="xcv x"
alias fsc="xcv c"
alias fsv="xcv v"
alias fsl="xcv l"
```

## Walkthrough Example

1. Start with a directory of files

  ```sh
  $ find .
  ./a.txt
  ./b.txt
  ./c
  ./c/d.txt
  ```

1. Then, **copy** all the files recursively

  ```sh
  $ xcv c -R .
  ```

1. Then, **list** the _copied_ files

  ```sh
  $ xcv l
  a.txt  b.txt  c
  ```

1. Then, change directories and **paste** in the _copied_ files

  ```sh
  $ cd ~/elsewhere
  $ xcv v
  ```

1. Then, list the _pasted_ files in the CWD, along with any pre-existing files

  ```sh
  $ ls
  a.txt  b.txt  c    x.txt
  ```

1. Then, **cut** all the files in the CWD

  ```sh
  $ xcv x *
  ```

1. Then, notice all the files have been _cut_ out

  ```sh
  $ ls
  ```

1. Then, change directories and **paste** in the _cut_ files

  ```sh
  $ cd ~/somewhere
  $ xcv v
  ```

1. Then, list the _pasted_ files in the CWD, along with any pre-existing files

  ```sh
  $ ls
  a.txt  b.txt  c    x.txt  y.txt
  ```

## License

ISC License (ISC)

Copyright &copy; 2015, Buster Collings

Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted, provided that the above copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
