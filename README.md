# Dotfiles

## How to install

The installation step requires the [XCode Command Line
Tools](https://developer.apple.com/downloads) and may overwrite existing
dotfiles in your HOME directory.

```bash
$ bash -c "$(curl -fsSL dotfiles.kevinmartensson.com)"
```

N.B. If you wish to fork this project and maintain your own dotfiles, you must
substitute my username for your own in the above command and the variable
found at the top of the `bin/dotfiles` script.

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
    <td><code>-l</code>, <code>--list</code></td>
    <td>List of additional applications to install</td>
  </tr>
  <tr>
    <td><code>-np</code>, <code>--no-packages</code></td>
    <td>Suppress package updates</td>
  </tr>
  <tr>
    <td><code>-ns</code>, <code>--no-sync</code></td>
    <td>Suppress pulling from the remote repository</td>
  </tr>
</table>


## Features

### Automatic software installation

Homebrew formulae:

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

Node packages:

* [bower](http://twitter.github.com/bower/)
* [grunt-cli](http://gruntjs.com/)
* [jshint](http://www.jshint.com/)

N.B. If your pre-existing Homebrew installation is not in `/usr/local` then you
must prepend your custom installation's `bin` to the PATH in
`.bash_profile.local`:

```bash
# Add `brew` command's custom location to PATH
PATH="/opt/acme/bin:$PATH"
```

### Custom OS X defaults

Custom OS X settings can be applied during the `dotfiles` process. They can
also be applied independently by running the following command:

```bash
$ osxdefaults
```

### Custom bash prompt

I use a custom bash prompt based on the Solarized color palette and influenced
by @gf3's and @cowboy's custom prompts. For best results, you should install
iTerm2 and import [Solarized
Dark.itermcolors](https://github.com/altercation/solarized/tree/master/iterm2-colors-solarized).

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

Further details are in the `bash_prompt` file.

### Local and private configurations

Any private and custom commands should be stored in a `~/.bash_profile.local`
file. Any commands included in this file will not be under version control or
committed to a public repository. If `~/.bash_profile.local` exists, it will be
sourced for inclusion in `bash_profile`.

Here is an example `~/.bash_profile.local`:

```bash
# PATH exports
PATH=$PATH:~/.gem/ruby/1.8/bin
export PATH

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
