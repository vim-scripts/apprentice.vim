# ![Apprentice](http://romainl.github.io/Apprentice/images/logo.png)

Apprentice is a low-contrast colorscheme for Vim based on the awesome [Sorcerer](http://www.vim.org/scripts/script.php?script_id=3299) by Jeet Sukumaran.

It’s essentially a streamlined version of the original with a reduced number of colors entirely taken from the default xterm palette to ensure a similar look in 256 colors-ready terminal emulators and GUI Vim.

JavaScript in GVim:

![JavaScript](http://romainl.github.io/Apprentice/images/apprentice_js.png)

Python in Gnome terminal with `TERM=xterm-256color`:

![Python](http://romainl.github.io/Apprentice/images/apprentice_py.png)

Vimscript in Gnome Terminal with `TERM=xterm`:

![Vim](http://romainl.github.io/Apprentice/images/apprentice_vim.png)

## Preparing your environment.

Apprentice is designed first and foremost to look “good” in terminal emulators supporting 256 colors and GUI Vim (GVim/MacVim). It supports less capable terminal emulators in the sense that you still get colors, but it will definitely look “better” in more powerful environments.

### GVim/MacVim

There’s nothing to do for GVim/MacVim as GUI Vim supports millions of colors by default.

### Terminal emulators

Most terminal emulators in use nowadays *can* display 256 colors but most of them use a default `TERM` that tells Vim otherwise. Assuming your terminal emulator actually supports 256 colors, you must instruct it to brag about its terminal-hood by setting the correct `TERM` environment variable.

Here are a bunch of common terminal emulators and their “ideal” `TERM`:

| Environment | Terminal emulator | Default `TERM` | ”Ideal” `TERM`          |
|-------------|-------------------|----------------|-------------------------|
| Mac OS X    | iTerm2.app        | `xterm`        | `xterm-256color`        |
| Mac OS X    | Terminal.app      | `xterm`        | `xterm-256color`        |
| X11         | xterm             | `xterm`        | `xterm-256color`        |
| X11         | URxvt             | `rxvt-unicode` | `rxvt-unicode-256color` |
| X11/Gnome   | Gnome terminal    | `xterm`        | `xterm-256color`        |
| X11/Gnome   | Terminator        | `xterm`        | `xterm-256color`        |
| X11/KDE     | Konsole           | `xterm`        | `xterm-256color`        |

Please refer to your terminal emulator’s manual for how to set it up properly.

NB: I’ve started [a wiki page](https://github.com/romainl/Apprentice/wiki/256-colors-and-you.) listing the procedures for the terminal emlators above.

For best results, it’s recommended to adjust your background color to the one used in Apprentice:

* xterm color: `235`
* hexadecimal color: `#262626`

### Terminal multiplexers

Screen and tmux don't respect your terminal emulator’s settings and set your `TERM` to their default value, `screen`. For better color support, the recommended `TERM` for both multiplexers is `screen-256color`.

#### tmux

Put this line in `~/.tmux.conf`:

    set -g default-terminal "screen-256color"

#### screen

Put this line in `~/.screenrc`:

    term "screen-256color"

## Installing Apprentice.

A colorscheme must be placed in a directory named `colors` that’s somewhere in Vim’s `runtimepath`:

The canonical location is:

    ~/.vim/colors/apprentice.vim

but it could be:

    ~/.vim/bundle/apprentice/colors/apprentice.vim

or whatever works for you.

Here are the most common installation methods:

### Manually:

1. Download [the latest release](https://github.com/romainl/Apprentice/releases/latest).
2. Unzip it somewhere on your machine.
3. Copy the file `colors/apprentice.vim` to `~/.vim/colors/apprentice.vim`.

### With [Pathogen](https://github.com/tpope/vim-pathogen):

#### The grumpy way:

1. Download [the latest release](https://github.com/romainl/Apprentice/releases/latest).
2. Unzip it under `~/.vim/bundle/`.

#### The hipster way:

    $ git clone https://github.com/romainl/Apprentice.git ~/.vim/bundle/apprentice

### With [Vundle](https://github.com/gmarik/Vundle.vim):

1. Add this line to your `~/.vimrc`, together with the rest of your `Plugin` lines:

        Plugin 'romainl/Apprentice'

2. Run this command to finish the installation:

        :PluginInstall

### With [NeoBundle](https://github.com/Shougo/neobundle.vim):

1. Add this line to your `~/.vimrc`, together with the rest of your `NeoBundle` lines:

        NeoBundle 'romainl/Apprentice'

2. Run this command to finish the installation:

        :NeoBundleInstall

Hmmm… I wonder where does that strange feeling of déjà-vu comes from?

## Enabling Apprentice.

To test Apprentice, just type this command from *normal* mode and hit `Enter`:

    :colorscheme apprentice

If you like what you see and want to make Apprentice your default colorscheme, add this line to your `~/.vimrc`, preferably near the end:

    colorscheme apprentice

---

If light colorschemes are more your thing, [Disciple](https://github.com/romainl/Disciple) is the negative version of Apprentice.
