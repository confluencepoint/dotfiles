# dotfiles

Dotfiles for bash, git, subl, etc.

## Getting started

* **OS X**: The [XCode Command Line Tools](https://developer.apple.com/downloads/) must be installed.
* **Windows**: [Git for Windows](https://msysgit.github.io/) must be installed.

The installation step may overwrite existing dotfiles in your `$HOME` directory.

```bash
$ bash -c "$(curl -fsSL raw.github.com/kevva/dotfiles/master/bin/dotfiles)"
```

## Features

### Automatic software installation

**Homebrew formulae**:

* GNU core utilities
* [git](http://git-scm.com/)
* [ack](http://betterthangrep.com/)
* [bash-completion](http://bash-completion.alioth.debian.org/)
* jpeg
* [node](http://nodejs.org/)
* [optipng](http://optipng.sourceforge.net/)
* [phantomjs](http://phantomjs.org/)
* [tree](http://mama.indstate.edu/users/ice/tree/)
* [wget](http://www.gnu.org/software/wget/)

**APT packages**:

* build-essentials
* [git-core](http://git-scm.com/)
* libssl-dev
* [nodejs](http://nodejs.org/)
* [sublime-text-installer](http://sublimetext.com/)
* [tmux](http://tmux.sourceforge.net/‎)
* [tree](http://mama.indstate.edu/users/ice/tree/)
* [wget](http://www.gnu.org/software/wget/)

**Node packages**:

* [bower](http://bower.io/)
* [grunt-cli](http://gruntjs.com//)
* [jshint](http://jshint.com/)
* [yo](http://yeoman.io/)

### Custom OS X defaults

Custom OS X settings can be applied during the `dotfiles` process. They can
also be applied independently by running the following command:

```bash
$ osxdefaults
```

### Custom bash prompt

When your current working directory is a Git repository, the prompt will
display the checked-out branch's name (and failing that, the commit SHA that
HEAD is pointing to). The state of the working tree is reflected in the
following way:

<table>
    <tr>
        <td><code>+</code></td>
        <td>Uncommitted changes in the index</td>
    </tr>
    <tr>
        <td><code>!</code></td>
        <td>Unstaged changes</td>
    </tr>
    <tr>
        <td><code>?</code></td>
        <td>Untracked files</td>
    </tr>
    <tr>
        <td><code>$</code></td>
        <td>Stashed files</td>
    </tr>
</table>

### Local and private configurations

Any private and custom commands should be stored in a `~/.bash_profile.local`
file. Any commands included in this file will not be under version control or
committed to a public repository. If `~/.bash_profile.local` exists, it will be
sourced for inclusion in `bash_profile`.

Here is an example `~/.bash_profile.local`:

```bash
# EDITOR export
export EDITOR="vim"

# Git credentials
# Not under version control to prevent people from
# accidentally committing with your details
GIT_AUTHOR_NAME="Kevin Martensson"
GIT_AUTHOR_EMAIL="kevva@example.com"
GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"

# Set the credentials (modifies ~/.gitconfig)
git config --global user.name "$GIT_AUTHOR_NAME"
git config --global user.email "$GIT_AUTHOR_EMAIL"
```

The `git/gitconfig` file is copied to `~/.gitconfig`, so any private git
configuration specified in `~/.bash_profile.local` will not be committed to
your dotfiles repository.

## License

[MIT License](http://en.wikipedia.org/wiki/MIT_License) (c) [Kevin Mårtensson](http://kevinmartensson.com)
