[Tmux](http://tmux.sourceforge.net/) is a terminal multiplexer. This tmux-config is forked from http://www.github.com/tony/tmux-config.git.

Feature
-------

- Support for [tmux-mem-cpu](http://github.com/thewtex/tmux-mem-cpu-load).
- Vim key-bindings.
- Zsh as default shell.
- Add [reattach-to-user-namespace](http://brewformulas.org/ReattachToUserNamespace) to accessing the Mac OS X pasteboard in tmux sessions.

Installation
------------

  Download:

```bash
git clone https://github.com/chichunchen/tmux-config.git ~/.tmux
```

  Copy tmux config to home:

```bash
ln -s ~/.tmux/.tmux.conf ~/.tmux.conf
```

  Go to config dir:

```bash
cd ~/.tmux
```

Stats
-----

### tmux-mem-cpu-load

(Linux-only)

  Prep ourself to download submodule:

```bash
git submodule init
```

  Download submodule:

```bash
git submodule update
```

  Change dir to tmux-mem-cpu-load:

```bash
cd ~/.tmux/vendor/tmux-mem-cpu-load
```

  General make file:

```bash
cmake .
```

  Compile our binary:

```bash
make
```

  Install our binary to `/usr/local/bin/tmux-mem-cpu-load`:

```bash
sudo make install
```

  Go home:

```bash
cd ~
```

  Launch tmux:
```
tmux
```
  And press `Control + b` then `d` to go back to the terminal.

  Update config:

```bash
tmux source-file ~/.tmux.conf
```

### basic-cpu-and-memory.tmux

(Cross platform, tested with python 2.7+)

Update March 19, 2014. Works with psutil 2.0 now.

  install ``psutil``

```bash
sudo pip install psutil
```

  copy ``~/.tmux/vendor/basic-cpu-and-memory.tmux`` to bin

```bash
sudo cp ~/.tmux/vendor/basic-cpu-and-memory.tmux /usr/local/bin/tmux-mem-cpu-load
```

  make executable

```bash
sudo chmod +x /usr/local/bin/tmux-mem-cpu-load
```

Start tmux
----------

  To start a session:

  `tmux`

  To reattach a previous session:

  `tmux attach`

  To reload config file

  `<Control + b>:` (which could Ctrl-B or Ctrl-A if you overidden it) then `source-file ~/.tmux.conf`

Commands
--------

  * `Control + b` before any command
  * `Control + b` then `?` to bring up list of keyboard shortcuts
  * `Control + b` then `"` to split window
  * `Control + b` then `<Space>` to change pane arrangement
  * `Control + b` then `o` to rotate panes
  * `Control + b` then `h`, `j`, `k`, `l` to move left, down, up, right. Respectively. (vim hjkl)
  * `Control + b` then `;` to go to last panel

  Beyond your first window:

  * `Control + b` then `c` to create a new window
  * `Control + b` then `n` to next window
  * `Control + b` then `p` to previous window
  * `Control + b` then `[0-9]` move to window number
  * `Control + b` then `&` to kill window


by Tony Narlock (tony@git-pull.com)

forked by Chi-Chun, Chen 
