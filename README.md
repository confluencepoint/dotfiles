# Dotfiles

My dotfiles for Windows and OS X.

## Prerequisites

* **OS X**: [XCode Command Line Tools](https://developer.apple.com/downloads)
* **Windows**: [Git for Windows](http://msysgit.github.com/)

## How to install

The installation step may overwrite existing dotfiles in your HOME directory.

```bash
$ bash -c "$(curl -fsSL https://raw.github.com/kevva/dotfiles/master/bin/dotfiles)"
```

The `.gitconfig` file is copied to the HOME directory so that any private git
configuration taking place is not accidentally committed. Everything else is
symlinked.

## How to update

You should run the update when:

* You make a change to `~/.dotfiles/git/gitconfig` (the only file that is
  copied rather than symlinked).
* You want to pull changes from the remote repository.
* You want to update Homebrew formulae and Node packages.

Run the dotfiles command:

```bash
$ dotfiles
```

Options:

<table>
  <tr>
    <td><code>-h</code>, <code>--help</code></td>
    <td>Help</td>
  </tr>
  <tr>
    <td><code>--no-packages</code></td>
    <td>Suppress package updates</td>
  </tr>
  <tr>
    <td><code>--no-sync</code></td>
    <td>Suppress pulling from the remote repository</td>
  </tr>
</table>

## Features

### Automatic software installation

Homebrew formulae (OS X):

* GNU core utilities
* [git](http://git-scm.com/)
* [ack](http://betterthangrep.com/)
* [bash-completion](http://bash-completion.alioth.debian.org/)
* libjpeg
* [macvim](http://code.google.com/p/macvim/)
* [node](http://nodejs.org/)
* [optipng](http://optipng.sourceforge.net/)
* [phantomjs](http://phantomjs.org/)
* [tree](http://mama.indstate.edu/users/ice/tree/)
* [wget](http://www.gnu.org/software/wget/)

Node packages:

* [bower](http://twitter.github.com/bower/)
* [grunt](http://gruntjs.com/)

### Custom OS X defaults

Custom OS X settings can be applied by running the following command:

```bash
$ osxdefaults
```

### Custom Windows defaults

Custom Windows settings can be applied by running the following command:

```bash
$ windefaults
```

## Adding local and private configurations

You can create a `~/.bash_profile.local` file to add private and custom
commands without the need to fork this repository. Any commands included in
this file will not be under version control or committed to a public
repository. If `~/.bash_profile.local` exists, it will be sourced for
inclusion in `bash_profile`.

Here is an example `~/.bash_profile.local`:

```bash
# PATH exports
PATH=$PATH:~/.gem/ruby/1.8/bin
export PATH

# Make vim the default editor
export EDITOR="vim"

# Git credentials
# Not under version control to prevent people from
# accidentally committing with your details
GIT_AUTHOR_NAME="Kevin Martensson"
GIT_AUTHOR_EMAIL="kevin@example.com"
GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"
# Set the credentials (modifies ~/.gitconfig)
git config --global user.name "$GIT_AUTHOR_NAME"
git config --global user.email "$GIT_AUTHOR_EMAIL"
```

## Acknowledgements

Inspiration and code was taken from many sources, including:

* [@necolas](https://github.com/necolas) (Nicolas Gallagher)
  [https://github.com/necolas/dotfiles](https://github.com/necolas/dotfiles)
* [@mathiasbynens](https://github.com/mathiasbynens) (Mathias Bynens)
  [https://github.com/mathiasbynens/dotfiles](https://github.com/mathiasbynens/dotfiles)
* [@tejr](https://github.com/tejr) (Tom Ryder)
  [https://github.com/tejr/dotfiles](https://github.com/tejr/dotfiles)
* [@gf3](https://github.com/gf3) (Gianni Chiappetta)
  [https://github.com/gf3/dotfiles](https://github.com/gf3/dotfiles)
* [@cowboy](https://github.com/cowboy) (Ben Alman)
  [https://github.com/cowboy/dotfiles](https://github.com/cowboy/dotfiles)
