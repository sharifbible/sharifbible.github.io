# sharifbible.github.io
Future home of the Sharif Bible website
## Table of Contents
* [Developing](#developing)
  * [MacOs](#macos)
  * [Windows](windows)
  * [Working with the site](#working-with-the-site)

## Developing
This website uses [Jekyll](https://jekyllrb.com) to generate the website from markdown, and the result is served from [GitHub Pages](https://pages.github.com). Everything needed to update this site should be contained in this repo.
 
### MacOS
You will need the following installed and up-to-date:
1. [Homebrew](https://brew.sh)

   You can install Homebrew from a Terminal with:
   ~~~ sh
   /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
   ~~~

2. [rbenv](https://github.com/rbenv/rbenv)

   Using Homebrew, you can install rbenv with:
   ~~~ sh
   brew install rbenv
   rbenv init
   ~~~
   Follow the instructions from `rbenv init`, then exit and start a new Terminal window.

3. Install the correct version of ruby

   With rbenv installed, you can now install the [correct version](.ruby-version) of Ruby. For example, if it is 2.5.1, run:
   ~~~ sh
   rbenv install 2.5.1
   rbenv rehash
   ~~~

4. [bundler](https://bundler.io)

   Next, install Bundler:
   ~~~ sh
   gem install bundler
   ~~~

5. Github setup

   You'll need a github account, and your environment set up correctly. To confirm, run:
   ~~~ sh
   ssh -T git@github.com
   ~~~

   You should see a response that indicates that you have successfully authenticated.

### Windows
(to do)

### Working with the site
With the environment set up on Mac or Windows, it's time to clone this repository:
~~~ sh
git clone git+ssh://git@github.com/sharifbible/sharifbible.github.io.git
git checkout develop
~~~

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
