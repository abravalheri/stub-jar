stub-jar
========

Given a runnable Java archive (or in other words, a `jar` file that can be
executed with the command `java -jar ...`), `stub-jar` can be used to generate
a executable file, as illustrated bellow:

```bash
$ stub-jar some.jar -o some-prog
```

Installation
------------

The following steps can be reproduced to perform a clean per-user installation.

1. Ensure [GNU Stow](https://www.gnu.org/software/stow/manual/stow.html) is
   installed and available:
   ```bash
   $ which stow
   ```
2. Choose a directory that will be the prefix for the installation
   (usually `~/.local`), and ensure it contains a `bin` subdirectory that
   is part of the `$PATH`:
   ```bash
   $ mkdir -p ~/.local/bin
   $ export PATH="$PATH:$HOME/.local/bin"
   # Something similar to the last command should be included in .bashrc,
   # .zshrc, ...
   ```
3. Choose a directory to store the project (usually `~/.local/stow`,
   `~/.local/packages` or `~/.local/software`) and clone the repository:
   ```bash
   $ mkdir -p ~/.local/stow && cd ~/.local/stow
   $ git clone https/github.com/abravalheri/stub-jar
   ```
4. Use GNU Stow:
   ```bash
   $ stow stub-jar
   # If the directory structure differs from the example, `-d` and `-t` options
   # can be used. See stow manual for more information.
   ```

Usage
-----

```
bin/stub-jar (--help | <jar_path> [-o <executable_path>])

  Create an executable from a jar file.
  Note that the jar file MUST be able to be executed with `java -jar`

Options:
  -h, --help	Display this message and exit
  -o, --output	Path where the executable stub should be generated
```

Credits
-------

This project is based on
[this coderwall post](https://coderwall.com/p/ssuaxa/how-to-make-a-jar-file-linux-executable).
