# dotfiles

Dotfiles for bash, git, subl, etc.

## Getting started

The installation step requires the [XCode Command Line
Tools](https://developer.apple.com/downloads) and may overwrite existing
dotfiles in your HOME directory.

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
* [tree](http://mama.indstate.edu/users/ice/tree/)
* [wget](http://www.gnu.org/software/wget/)

**Node packages**:

* [bower](http://bower.io/)
* [component](http://component.io/)
* [gulp](http://gulpjs.com/)
* [jshint](http://jshint.com/)
* [yo](http://yeoman.io/)

**Atom packages**:

* [autoprefixer](http://atom.io/packages/autoprefixer)
* [editorconfig](http://atom.io/packages/editorconfig)
* [jshint](http://atom.io/packages/jshint)
* [language-jade](http://atom.io/packages/language-jade)
* [sort-lines](http://atom.io/packages/sort-lines)
* [spacegray-dark-ui](http://atom.io/packages/spacegray-dark-ui)
* [travis-ci-status](http://atom.io/packages/travis-ci-status)
* [uglify](http://atom.io/packages/uglify)
* [visual-bell](http://atom.io/packages/visual-bell)

### Custom OS X defaults

Custom OS X settings can be applied during the `dotfiles` process. They can
also be applied independently by running the following command:

```bash
$ osxdefaults
```

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
