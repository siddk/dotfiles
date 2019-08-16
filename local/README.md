New Machine Setup:

1. Install iTerm 2
2. Nord Color Theme: https://github.com/arcticicestudio/nord-iterm2
3. Remap Caps Lock to Control: http://www.drbunsen.org/remapping-caps-lock/

4. Install zsh and Prezto (Configuration Framework): https://github.com/sorin-ionescu/prezto
	- >>> zsh 
	- >>> git clone --recursive https://github.com/sorin-ionescu/prezto.git "${ZDOTDIR:-$HOME}/.zprezto" (Clone in Prezto)
	- >>> setopt EXTENDED_GLOB (copy dot files from prezto repo)
                  for rcfile in "${ZDOTDIR:-$HOME}"/.zprezto/runcoms/^README.md(.N); do
                      ln -s "$rcfile" "${ZDOTDIR:-$HOME}/.${rcfile:t}"
                  done
	- >>> chsh -s /bin/zsh (change default shell to zsh)
	- >>> Activate history-substring-search, syntax-highlighting, osx, git, homebrew, python (zstyle ':prezto:module:python' skip-virtualenvwrapper-init 'on' | zstyle ':prezto:module:python' conda-init 'on' )


5. Install Homebrew 
	- >>> /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
	- >>> Install/Upgrade Git
		 brew install git
		 brew link --force git

6. Terminal Aesthetics:
	- >>> Install the Iovclaska font
		 https://github.com/chrissimpkins/codeface/tree/master/fonts/inconsolata-dz		 Set it as the default font in iTerm by going to Preferences > Profiles > Text > Change Font
		 Use 18pt for the font size, and set up iTerm Hotkey
	
	- >>> Install Nord dircolors
		 brew install coreutils
		 cp dotfiles/dircolors ~/.dircolors

		 Add following to .zshrc:

		 PATH="/usr/local/opt/coreutils/libexec/gnubin:$PATH"
 	         MANPATH="/usr/local/opt/coreutils/libexec/gnuman:$MANPATH"
	         test -e ~/.dircolors && \ 
   		     eval `dircolors -b ~/.dircolors`
	         alias ls="ls --color=always" 
	         alias grep="grep --color=always"
	         alias egrep="egrep --color=always"

	- >>> Use the Nabla theme
		 - brew install shpotify
		 
7. Install vim
    - >>> brew install vim
    
    - Install Vundle (Plugin Manager)
        - >>> git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
    
    - Use Provided .vimrc 
    
    - Install YCM
        - >>> brew install cmake
        - >>> cd ~/.vim
        - >>> mkdir ycm_build 
        - >>> cd ycm_build
        - >>> cmake -G "Unix Makefiles" . ~/.vim/bundle/YouCompleteMe/third_party/ycmd/cpp
        - >>> cmake --build . --target ycm_core --config Release
        
    - Get NerdTree working
    
8. Get Tmux working
    - Install TPM (Package Manager) :: >>> git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
    - Install Nord Color Scheme for TMUX - https://github.com/arcticicestudio/nord-tmux
    
9. Install Python 3, Pytorch, Visdom, and other necessary libs
    - Install anaconda: https://www.anaconda.com/download/#macos
    - Export anaconda bin to PATH: export PATH="/<path to anaconda>/bin:$PATH"
    - >>> conda install pytorch torchvision -c pytorch
    - >>> conda install ipython
    - >>> conda install jupyter
    - >>> conda install -c conda-forge visdom 

    


    
        