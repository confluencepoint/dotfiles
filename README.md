# Dotfiles

My Windows dotfiles.

## Installation

You need to install the [Git for Windows](http://msysgit.github.com/) prior to
installing these dotfiles.

The installation step may overwrite existing dotfiles in your HOME directory.

```bash
bash -c "$(curl -fsSL https://raw.github.com/kevva/dotfiles/master/bin/dotfiles)"
```

The `.gitconfig` file is copied to the HOME directory so that any private git
configuration taking place is not accidentally committed. Everything else is
symlinked.

## What else does it install?

via npm

* [bower](http://twitter.github.com/bower/)
* [grunt](http://gruntjs.com/)

## Updating

This must be done when:

* You make a change to `~/.dotfiles/git/gitconfig` (the only file that isn't symlinked).
* You want to pull and apply changes from the remote repository.
* You want to update packages.

```bash
dotfiles
```

There are options available to suppress package updates and/or pulling from the remote repository.

```bash
dotfiles --no-packages --no-updates
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
