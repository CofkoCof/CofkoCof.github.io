---
title: Yekyll installation
date: 2023-09-03 09:00.00 +0000
categories: [Yekyll, Blogs]
tags: [yekyll,blogs]
---

# Yekyll Installation
Jekyll is a static site generator, that renders Markdown or Textile and Liquid templates, and produces a static website ready to be served by web server.

## Ubuntu
### Install prerequisites
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```
### Set environment variables
```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### Install Yekyll and Bundler
```bash
gem install jekyll bundler
```

### Build and run locally
#### Build
To build the site, set the environment variable to production and run the following command

```bash
JEKYLL_ENV=production bundle exec jekyll b
```

#### Run
Start the website on localhost with

```bash
bundle exec jekyll s
```

### Errors
If you encounter error similiar to below

```
sass-embedded-1.63.6-x86_64-linux-musl requires rubygems version >= 3.3.22, which is incompatible with the current version, 3.1.2
```

follow below steps

```bash
rvm install 3.0
rvm use 3.0.0 -default
rvm -v
rvm gemset update
gem install jekyll
jekyll -v
```

If first command gives you error that rvm is not installed, you can fix it with

```bash
sudo apt-get install software-properties-common

sudo apt-add-repository -y ppa:rael-gc/rvm
sudo apt-get update
sudo apt-get install rvm

sudo usermod -a -G rvm $USER

reboot
```