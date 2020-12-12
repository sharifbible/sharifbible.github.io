# sharifbible.github.io
Future home of the Sharif Bible website
## Table of Contents
* [Developing](#developing)
  * [MacOs](#macos)
  * [Windows](windows)
  * [Working with the site](#working-with-the-site)
  * [Making changes](#making-changes)

## Developing
This website uses [Jekyll](https://jekyllrb.com) to generate the website from markdown, and the result is served from [GitHub Pages](https://pages.github.com). Everything needed to update this site should be contained in this repo.
 
### MacOS
You will need the following installed and up-to-date:
1. You can install [Homebrew](https://brew.sh) from a Terminal with:
   ~~~ sh
   /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
   ~~~

2. Using Homebrew, you can install [rbenv](https://github.com/rbenv/rbenv) with:
   ~~~ sh
   brew install rbenv
   rbenv init
   ~~~
   Follow the instructions from `rbenv init`, then exit and start a new Terminal window.

3. With rbenv installed, you can now install the [correct version](.ruby-version) of Ruby. For example, if it is 2.7.1, run:
   ~~~ sh
   rbenv install 2.7.1
   rbenv rehash
   ~~~

4. Next, install [bundler](https://bundler.io):
   ~~~ sh
   gem install bundler
   ~~~

5. You'll need a github account, and your environment set up correctly. If you don't already have a key-pair, start with generating one:
   ~~~ sh
   ssh-keygen -t rsa -b 4096 -C "your-github-email@example.com"
   ~~~
   You can choose to save that key in a new file, or accept the default. Then, copy the public key to your clipboard:
   ~~~ sh
   pbcopy < ~/.ssh/id_rsa.pub
   ~~~
   In your github account, under Settings | SSH and GPG Keys, paste the key into a new SSH Key. Then, add your key to your mac keychain:
   ~~~ sh
   ssh-add -K ~/.ssh/id_rsa
   ~~~
   To confirm that you are configured correctly, run:
   ~~~ sh
   ssh -T git@github.com
   ~~~
   You should see a response that indicates that you have successfully authenticated.

### Windows
You will need the following installed and up-to-date:
1. Install WSL (Ubuntu) from the Windows App Store
2. From the new terminal, run:
    ~~~ sh
    curl -sL https://github.com/rbenv/rbenv-installer/raw/master/bin/rbenv-installer | bash -
    echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
    echo 'eval "$(rbenv init -)"' >> ~/.bashrc
    source ~/.bashrc 
    rbenv init
    sudo apt-get install -y build-essential git libreadline-dev libssl-dev zlib1g-dev
    rbenv install 2.7.1
    rbenv local 2.7.1
    rbenv rehash
    gem install bundler
    rbenv rehash
    bundle install
    ~~~ 



### Working with the site
With the environment set up on Mac or Windows, it's time to clone this repository:
~~~ sh
git clone git+ssh://git@github.com/sharifbible/sharifbible.github.io.git
cd sharifbible.github.io
git checkout develop
~~~
Now, use bundle to install all the necessary gems:
~~~ sh
bundle install
~~~
Then, test out the site by running Jekyll:
~~~ sh
bundle exec jekyll serve
~~~
And navigate to the url (default is localhost:4000 or 127.0.0.1:4000). You should see the site.

### Making changes
All work on the site must be done in a branch off develop, so when you're ready to do your work, run:
~~~ sh
git fetch --all
git checkout -b feature/a-short-feature-name develop
~~~

Make small changes at a time, saving your work, and then commit:
~~~ sh
git commit -a -m "a brief message describing the change"
~~~

Commit early and often.

Finally, when you're ready to wrap up all the work you've done, push it up to github:
~~~ sh
git push -u origin feature/a-short-feature-name
~~~

## Other Notes
Regularly run `bundle update` to ensure we're on the latest versions. Driven by github-pages dependencies described at https://pages.github.com/versions/

