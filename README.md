This is my folder housing some config files to make set up
on a clean new machine fast and easy.

### Setup on new machine
- Remove local .vim folder
- `git clone git@github.com:naf445/new-machine.git`
- `mv new-machine/ .new-machine/`
- In home directory: `echo 'runtime vimrc' > .vimrc`
- `ln -s .new-machine/vim/ .vim`
- `cd .vim` --> `vim vimrc` and plugins will prob download but there will prob be some errors
- if colors look weird on linux machine, you may have to create an alias for command `tmux` which makes it run `tmux -2`
- symlink tmux config 
    * `ln -s .new-machine/tmux/.tmux.conf .tmux.conf`
- If mac, install homebrew
    * `ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" < /dev/null 2> /dev/null`
- install TMUX
    * `brew install tmux`
- set vim as default editor:
    * export VISUAL=vim
    * export EDITOR="$VISUAL"
- Install pip
    * `curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py`
    * `python3 get-pip.py`
- Potentially need to add python3.7/bin location to terminal emulator app path variable 
- Install cheat
    * `pip install cheat`
- remove initial cheat folder and symlink your cheat folder
    * `rm -R .cheat`
    * `ln -s .new-machine/cheat/ .cheat`


 
### Jupyter-vim plugin specific, but prob important anyways to avoid errors
- Check system python type with `:pythonx import sys; print(sys.version)`
- Make sure you have virtualenv installed, if not pip install it
- Create a virtual environment referencing the system python which vim was compiled on
- Something like `virtualenv -p /usr/local/bin/python3.7 /path/to/my/new/vim_virtualenv`
- In your .bashrc, add a line to export a variable called VIM_VIRTUALENV_PATH with that path, full name not with the ~ character
- `source virtualenvs/vim_virtualenv/bin/activate`
- `pip install jupyter` 
