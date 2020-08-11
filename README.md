This is my folder housing some config files to make set up
on a clean new machine fast and easy.

### Setup on new machine
- Remove local .vim folder
- `git clone git@github.com:naf445/new-machine.git`
- `mv new-machine/ .new-machine/`
- In home directory: `echo 'runtime vimrc' > .vimrc`
- `ln -s .new-machine/vim/ .vim`
- `cd .vim` --> `vim vimrc` and plugins will prob download but there will prob be some errors
- if colors look weird on linux machine, you may have to create an alias for tmux which makes tmux run tmux -2

### Jupyter-vim plugin specific, but prob important anyways to avoid errors
- Check system python type with `:pythonx import sys; print(sys.version)`
- Make sure you have virtualenv installed, if not pip install it
- Create a virtual environment referencing the system python which vim was compiled on
- Something like `virtualenv -p /usr/local/bin/python3.7 /path/to/my/new/vim_virtualenv`
- Go back into vimrc and change the `let g:vim_virtualenv_path = '/home/sodflo/virtualenvs/vim_virtualenv'` line to reflect where your new virtualenv is
- `source virtualenvs/vim_virtualenv/bin/activate`
- `pip install jupyter` 
