# OSX developer environment setup

First of all you need homebrew, the package manager for OSX:

```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

When prompted to install Xcode, accept and install.

Now that homebrew is set up just paste this into your terminal:

```bash
brew update
brew install vim

# Install Cask and stuff
brew tap caskroom/cask
brew cask install iterm2
brew cask install spotify
brew cask install google-chrome
```

```bash
# Get the latest git version
brew install git

# Make sure OSX uses our own installs
echo "export PATH=/usr/local/bin:$PATH" >> ~/.bash_profile

# Install pathogen, for vim plugins
mkdir -p ~/.vim/autoload ~/.vim/bundle
curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim

echo "execute pathogen#infect()" >> ~/.vimrc
cd ~/.vim/bundle
git clone https://github.com/tpope/vim-pathogen.git
git clone https://github.com/scrooloose/nerdtree.git ~/.vim/bundle/nerdtree
git clone https://github.com/altercation/vim-colors-solarized.git ~/.vim/bundle/vim-colors-solarized

# Install nvm and node
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.31.1/install.sh | bash
source ~/.bash_profile

nvm install 4.4.5
nvm install node

# Install and set up go
brew install go
echo "export PATH=$PATH:/usr/local/opt/go/libexec/bin" >> ~/.bash_profile
echo "export GOPATH=$HOME/code/go" >> ~/.bash_profile
mkdir -p ~/code/go/src/github/jahrlin

# Reload bash_profile
source ~/.bash_profile

# Done!
echo "Done!"
```
