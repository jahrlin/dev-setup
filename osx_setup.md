# OSX developer environment setup

First of all you need homebrew, the package manager for OSX:

```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

When prompted to install Xcode, accept and install.

Now that homebrew is set up just paste this into your terminal:

```bash
# Get the latest git version
brew install git

# Make sure OSX uses our own installs
echo "export PATH=/usr/local/bin:$PATH" >> ~/.bash_profile

# Install vim
brew install vim

# Install and set up go
brew install go
echo "export PATH=$PATH:/usr/local/opt/go/libexec/bin" >> ~/.bash_profile
echo "export GOPATH=$HOME/code/go" >> ~/.bash_profile
mkdir -p ~/code/go/src/github/jahrlin

# Reload bash_profile
source ~./bash_profile

# Done!
echo "Done!"
```
