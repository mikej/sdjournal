---
title: Installing Ruby with rbenv on Debian
---

Quick guide to installing Ruby versions on Debian using [rbenv](https://github.com/sstephenson/rbenv/)

1. Ensure dependencies are installed using `apt-get install gcc make zlib1g zlib1g-dev`
2. If you want to use the version of git from Debian and don’t have that installed yet then install that too: `apt-get install git`
2. Clone rbenv from GitHub: `git clone git://github.com/sstephenson/rbenv.git ~/.rbenv`
3. Install the ruby-build plugin: `git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build`
4. Add ~/.rbenv/bin to your $PATH for access to the rbenv command-line utility: `echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.profile`
4. Enable shims and command line autocompletion: `echo 'eval "$(rbenv init -)"' >> ~/.profile`
5. Restart your shell
6. Install ruby: e.g. `rbenv install 1.9.3-p392`
7. Rebuild the shim executables: `rbenv rehash`
8. Set the rbenv global version of Ruby to the one just installed: e.g. `rbenv global 1.9.3-p392`

****
After installing, if you get the error `no such file to load -- zlib (LoadError)` when trying to install any gems this is likely because you are missing zlib1g or zlib1g-dev. You will need to `apt get install zlib1g zlib1g-dev` and then recompile Ruby again by rerunning `rbenv install`.