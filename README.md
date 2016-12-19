# OSX developer environment setup

First of all you need homebrew, the package manager for OSX:

```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

When prompted to install Xcode, accept and install.

Now that homebrew is set up just paste this into your terminal:
```zsh
# Install zsh and oh-my-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# Get the latest git version
brew install git

# Get my dotfiles
git clone https://github.com/jahrlin/dotfiles.git

rm ~/.zshrc
ln -s ~/dotfiles/zsh/.zshrc ~/.zshrc

rm ~/.vimrc
ln -s ~/dotfiles/vim/.vimrc ~/.vimrc
```

```zsh
brew update
brew install vim

# Install Cask and stuff
brew tap caskroom/cask
brew cask install iterm2
brew cask install spotify
brew cask install google-chrome
```

```bash
# Install pathogen, for vim plugins
mkdir -p ~/.vim/autoload ~/.vim/bundle
curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim

echo "execute pathogen#infect()" >> ~/.vimrc
cd ~/.vim/bundle
git clone https://github.com/tpope/vim-pathogen.git
git clone https://github.com/scrooloose/nerdtree.git
git clone https://github.com/altercation/vim-colors-solarized.git
git clone https://github.com/yssl/QFEnter.git
git clone https://github.com/mileszs/ack.vim.git
git clone https://github.com/ctrlpvim/ctrlp.vim.git
git clone https://github.com/vim-airline/vim-airline.git
git clone https://github.com/bling/vim-bufferline.git
git clone https://github.com/tpope/vim-fugitive.git
git clone https://github.com/scrooloose/syntastic.git
git clone https://github.com/blueshirts/darcula.git
git clone https://github.com/jiangmiao/auto-pairs.git

# Install nvm and node
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.1/install.sh | bash
source ~/.bash_profile

nvm install 4.4.5
nvm install node

# Install and set up go
brew install go
echo "export PATH=$PATH:/usr/local/opt/go/libexec/bin" >> ~/.zshrc
echo "export GOPATH=$HOME/code/go" >> ~/.zshrc
mkdir -p ~/code/go/src/github/jahrlin

# Reload zsh
source ~/.zshrc

# Done!
echo "Done!"
```
