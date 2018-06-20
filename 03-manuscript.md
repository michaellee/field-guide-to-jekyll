# Introduction

*Jekyll: A static-site generator written in Ruby.*

In other words, a program written in the Ruby programming language, that allows you to make websites that look and feel dynamic but are actually made from files and not a database.

In this guide, I'll be showing you how to get Jekyll installed on your machine so you can start making awesome sites.

Static-site, Jekyll, no database, they all sound great but really what's so awesome about all this?
Well, let me share with you a story about a guy named Tom. Tom was a guy with a lot of cool ideas. And as someone who had a ton of cool ideas, he started a bunch of blogs to share his ideas. He had a blog for things he was learning about, such as the Ruby programming language and at one point he was really into Jeeps so he had one on Jeeps as well.

Tom had a ton of cool stuff to share with the Internet, but instead of writing, he kept having to update his blogging software, Wordpress. With a dynamic blogging software like Wordpress he had to worry about updates for security problems and his databases going bad. All this trouble eventually led to Tom abandoning those sites and often without any copies of the content he had created. :'(

Tom grew tired of maintaining Wordpress, databases and losing his content; so he created a software to fix his problems. If you haven't already guessed, the Tom in this story is Tom Preston-Werner, the creator of Jekyll. Jekyll is Tom's solution to making it super easy to add content online and not have to worry about anything once it is on there.

## Sweet let's do this!
Now that you know what makes Jekyll so sweet, the rest of this guide will show you how to get Jekyll installed on your machine. I'll be covering how to install Jekyll on both macOS and Ubuntu since those are the two systems I'm most familiar with. The steps in this guide are the same exact steps that I take when setting up Jekyll on a new machine. You could find shorter instructions on getting Jekyll up and running but from my experience this is a much better setup.

## Before we start
This guide assumes that you've never installed Jekyll on your system. Although it helps to be comfortable with the command line, it is not necessary. Commands that should be run are included in this guide and could be easily copied and pasted into your terminal. For this reason it is best to view this book on the machine where Jekyll will be installed.
<div style="page-break-after:always;"></div>

# Installing Jekyll on macOS

## Open Terminal

First thing we'll need to do is locate *Terminal* which comes included with macOS.

There are two ways you can get to *Terminal*.

First you could use *Spotlight* to search for Terminal. To prompt Spotlight, either **click** on the Spotlight icon in the top right corner of your screen (looks like a magnifying glass) in the menubar or press **command and the spacebar**. When the *Spotlight Search* bar appears, **type** in *Terminal*.

The other way in finding Terminal is by using *Finder*. Open up a Finder window, then **click** on *Go* in the menu bar. When the Go menu appears, click on the *Applications* option. Once the Applications folder is open in Finder, **open** the folder labeled *Utilities*. You'll find Terminal within there. Simply double-click to open *Terminal*.

## Install Homebrew

Now that we've got Terminal open, we'll need to install *Homebrew*. Homebrew is known as the missing package manager for macOS. There are other ways to install some of the software needed to get Jekyll up and running, but I've found Homebrew to be the easiest on the Mac.

Homebrew makes it super easy to get programs and libraries onto your Mac using a simple command that starts with `brew`. If you aren't the most comfortable with installing things on your own via the Terminal, Homebrew is great for that. It helps you manage software on your machine with what they refer to as packages.
<div style="page-break-after:always;"></div>
For now, let's install Homebrew on your machine. To do so, simply **copy and paste** the command into your *Terminal* window.

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

If you don't have Xcode installed, it'll ask if you'd like to install the command line developer tools. You have the option of installing just the command line tools or you could install Xcode, which is the IDE for developing iOS and macOS apps. Installing Xcode will also install the command line developer tools. If you would like just the command line tools then **Hit yes**. If you would like to install Xcode, hit *Get Xcode*.

If you decide to install Xcode, you'll have to accept the *License agreement*. After accepting the agreement, Xcode will continue to install the necessary components. When Xcode is done, go back to your Terminal and **hit return** to continue.

After brew is done installing, **type** in `brew doctor` in your Terminal and you should get *Your system is ready to brew*. Now Homebrew is installed on your machine and we can move on to installing *rbenv*.

## Install rbenv

Now that we've got Homebrew on our system, we'll be installing *rbenv*. What rbenv allows you to do is manage different versions of Ruby on your machine. Out of the box, macOS comes with a copy of Ruby, but I've found that using rbenv to manage different versions of Ruby to be beneficial.

For example, if you're working on a Ruby on Rails project with someone else, their project might require a different version of Ruby than the one on your machine. If this is the case you would have to either install the version of Ruby required by the project, thus overwriting yours. Or you could use rbenv to load up different versions of Ruby based on what is specified by the project.

To install *rbenv* via Homebrew, **type** in `brew install rbenv ruby-build` in your terminal window and hit return.

Let me break down what this command is doing. `brew` which is the first part of the command tells Terminal that you want to run a *Homebrew* command. `install` is telling *brew* that you want to install a piece of software or what they call a package. `rbenv ruby-build` is telling *brew* you want to install the packages for rbenv and the rbenv plugin called *ruby-build*.

For more information about rbenv and ruby-build, check out the respective Github repositories [here](https://github.com/rbenv/rbenv) and [here](https://github.com/rbenv/ruby-build).

Once rbenv is installed, you'll need to run `rbenv init`. What this does is gives you instructions on how to get rbenv to load automatically each time a new Terminal session begins. For more information about this step, please check out this step on the [rbenv GitHub repo](https://github.com/rbenv/rbenv#how-rbenv-hooks-into-your-shell).

## Install Ruby

Now that you've got rbenv installed on your machine along with it's plugin *ruby-build*, we can install a version of *Ruby*. Ruby is a programming language that was created by a Japanese man named, Yukihiro Matsumoto, also known as Matz. The Ruby programming language grew to popularity as the web framework, Ruby on Rails became widely adopted as a standard in how web applications were built.

Like Ruby on Rails, Jekyll is also written in Ruby. Knowledge of the Ruby programming language isn't necessary to build websites with Jekyll, but if you are interested in learning more about the language, I highly recommend checking out [Codecademy's free course on learning Ruby](https://www.codecademy.com/learn/ruby).

As of Jekyll version 3 (which is the version this guide and my book covers), a minimum of *Ruby* version 2 and above is recommended to be installed on your machine. I personally try to install the latest stable version of Ruby that is listed on the [Ruby download page](https://www.ruby-lang.org/en/downloads/). As of this writing, the latest stable version is 2.4.1. For this reason, I'll be using 2.4.1 in the instructions below.

If you would like to install a different version of *Ruby*, rbenv has a command that will let you list out all the versions of Ruby available. That command is `rbenv install --list`.

To install Ruby version 2.4.1 you'll want to run this command in Terminal.

```
rbenv install 2.4.1
```

It takes a while to install *Ruby* so I suggest going on a short walk, grabbing a bite to eat or checking out some YouTube videos like this feel good video from Stuart Edge called *[Surpise Group Hug](https://youtu.be/44tmIiInBwg)*.

## Set global Ruby version

At this point we've got Ruby installed via *rbenv* but we're not using the version we just installed yet. If you type in `ruby -v` it'll show you that you're using macOS' default version of Ruby which came with your machine.

On my Mac, which is running macOS - Sierra, typing in `ruby -v` returns:

```
ruby 2.0.0p648 (2015-12-16 revision 53162) [universal.x86_64-darwin16]
```

This isn't version 2.4.1, the version we installed with *rbenv*.

To start using version 2.4.1 we'll have to tell *rbenv* to set the version of Ruby to use. You do this by **typing** in `rbenv global 2.4.1` in your Terminal and hitting return.

What this does is tells rbenv to globally use Ruby version 2.4.1 as the Ruby version of choice on your machine. Behind the scenes, rbenv writes the version number you've specified in a file located at `~/.rbenv/version`.

Now when you type `ruby -v` you should get something like this:

```
ruby 2.4.1p111 (2017-03-22 revision 58053) [x86_64-darwin16]
```

This is the version of *Ruby* you installed with rbenv.

## Installing Jekyll

Now that you've got Ruby up and running on your machine, this is the moment we've all been waiting for, installing *Jekyll*. To install Jekyll we'll be using *gem* which is Ruby's package manager for installing Ruby programs and libraries.

**Type** in `gem install jekyll` in your Terminal and hit return.

Jekyll will install, along with all of its dependencies. Once it's all done, we'll need to tell rbenv to see it so that we could use the Jekyll command-line tool. You do this by **typing** `rbenv rehash` in your Terminal and hitting return.

If you're wondering about what rehash does, it installs "shims" so that when a Ruby program or library gets executed, it runs with the correct version of Ruby. Again this is helpful in scenarios where you've got different versions of Ruby installed. Along with the different version of Ruby for a project, the project might also use different versions of a library. shims helps sort this out.

Now if we **type** `jekyll -v` in Terminal, we should see `jekyll 3.5.0` which is the latest version of Jekyll version 3 at the time of writing.

Wooohoooo! We've now got Jekyll installed on our Mac and ready to make websites!

# Installing Jekyll on Ubuntu

## Open Terminal

First thing we'll need to do is locate *Terminal* which comes included with Ubuntu.

You could access Terminal, by **clicking** on *Dash* in the menu bar. Dash is the icon that has the Ubuntu logo on it. When Dash's search prompt comes up, **type in** *Terminal*, when the Terminal icon appears, **click on it** to open.

Another convenient way to get to Dash's search prompt is by **hitting** the *super* and *a* key on your keyboard. If you're using a Windows based keyboard, the super key is mapped to the Windows key.

## Install git

First thing we'll want to do in Terminal is install *git*. git is a versioning system used for developers to take snapshots of a project. It is useful in that it allows you to make changes and if you aren't happy with a change you can revert back to a previous version. git also shines when working in teams.

To install git, **type** this into your Terminal.

```
sudo apt-get install git-core
```

Upon using the `sudo` command it will ask you for your password. Type it in and hit return.

## Install Ruby's dependencies

Before we install Ruby on your machine, we'll need to grab a few of its dependencies.

```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

First we'll want to make sure we've got the latest version of the package lists to get the latest versions of the dependencies.

```
sudo apt-get update
```

Once the packages are updated, we can now install the dependencies we'll need.

```
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev nodejs yarn
```

## Install rbenv

Now that we've got all of Ruby's dependencies on our system, we'll be installing *rbenv*. What rbenv allows you to do is manage different versions of Ruby on your machine. Using rbenv to manage different versions of Ruby can be beneficial.

For example, if you're working on a Ruby on Rails project with someone else, their project might require a different version of Ruby than the one on your machine. If this is the case you would have to either install the version of Ruby required by the project, overwriting yours. Or you could use rbenv to load up different versions of Ruby based on what is specified by the project.

To install *rbenv*, you'll want to **run** this command from your Terminal.

```
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
```

What this command does is, calls the `git` command. `clone` is telling *git* that you want to clone an existing project. `https://github.com/rbenv/rbenv.git` is the location of the existing git repository. `~/.rbenv` is the path in which you want to clone the existing git project which is in a dot folder in your home directory.

Once you've cloned rbenv, you'll have to add `~/.rbenv/bin` to your `$PATH` to access the `rbenv` command-line utility. To do so you'll want to **type** this into Terminal.

```
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
```

Next we'll add `rbenv init` to your shell to enable shims and autocompletion.

```
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL
```

**Restart your shell** so that PATH can take effect. Either opening a new terminal or closing and reopening your current one.

To make sure rbenv is working properly, **type** `type rbenv` into your Terminal which should yield.

`"rbenv is a function"`

Now that we've got *rbenv* installed, we'll need to install a plugin for it called, *ruby-build*. What *ruby-build* provides is an easy to use `install` command for rbenv to compile and install different versions of Ruby.

To install run this command in your Terminal.

```
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```

Next we'll need to give access to ruby-build to your `$PATH` by typing this into Terminal.

```
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL
```

For more information about rbenv and ruby-build, check out the respective Github repositories [here](https://github.com/rbenv/rbenv) and [here](https://github.com/rbenv/ruby-build).

## Install Ruby

Now that you've got *rbenv* installed on your machine along with it's plugin *ruby-build*, we can install a version of Ruby. Ruby is a programming language that was created by a Japanese man named, Yukihiro Matsumoto, also known as Matz. The Ruby programming language grew to popularity as the web framework, Ruby on Rails became widely adopted as a standard in how web applications were built.

Like Ruby on Rails, Jekyll is also written in Ruby. Knowledge of the Ruby programming language isn't necessary to build websites with Jekyll, but if you are interested in learning more about the language, I highly recommend checking out [Codecademy's free course on learning Ruby](https://www.codecademy.com/learn/ruby).

As of Jekyll version 3 (which is the version this guide and my book covers), a minimum of Ruby version 2 and above is recommended to be installed on your machine. I personally try to install the latest stable version of Ruby that is listed on the [Ruby download page](https://www.ruby-lang.org/en/downloads/). As of this writing, the latest stable version is 2.4.1. For this reason, I'll be using 2.4.1 in the instructions below.

If you would like to install a different version of Ruby, rbenv has a command that will let you list out all the versions of Ruby available. That command is `rbenv install --list`.

To install Ruby version 2.4.1 you'll want to run this command in Terminal.

```
rbenv install 2.4.1
```

It takes a while to install *Ruby* so I suggest going on a short walk, grabbing a bite to eat or checking out some YouTube videos like this feel good video from Stuart Edge called *[Surpise Group Hug](https://youtu.be/44tmIiInBwg)*.

## Set global Ruby version

We've got Ruby installed via *rbenv* but we're not using the version we just installed yet. To start using version 2.4.1 we'll have to tell *rbenv* to set the version of Ruby to use. You do this by typing in `rbenv global 2.4.1` in your Terminal and hitting return.

What this does is tells rbenv to globally use Ruby version 2.4.1 as the Ruby version of choice on your machine. Behind the scenes, rbenv writes the version number you've specified in a file located at `~/.rbenv/version`.

Now when you type `ruby -v` you should get something like this:

```
ruby 2.4.1p111 (2017-03-22 revision 58053) [x86_64-linux]
```

Which is the version of Ruby you installed with rbenv.

## Installing Jekyll

Now that you've got Ruby up and running on your machine, here is the moment we've all been waiting for, installing *Jekyll*. To install *Jekyll* we'll be using *gem* which is Ruby's package manager for installing Ruby programs and libraries.

**Type** in `gem install jekyll` in your Terminal and hit return.

Jekyll will install along with all of its dependencies. Once it's all done, we'll need to tell rbenv to see it so that we could use the Jekyll command-line tool. You do this by typing `rbenv rehash`.

If you're wondering about what rehash does, it installs "shims" so that when a Ruby program or library gets executed, it runs with the correct version of Ruby. Again this is helpful in scenarios where you've got different versions of Ruby installed. Along with the different version of Ruby for a project, the project might also use different versions of a library. shims helps sort this out.

Now if we type `jekyll -v` in Terminal, we should see `jekyll 3.5.0` which is the latest version of Jekyll version 3 at the time of writing.

Wooohoooo! We've now got Jekyll installed on our Ubuntu machine and ready to make websites!

# Create a new Jekyll project

Now that we've got Jekyll up and running on your machine, let's create a new *Jekyll* project to start playing around with Jekyll.

In the following command we'll be running, feel free to change `myawesomeblog` with whatever you would like the name of your Jekyll project folder to be. Once you've decided on a name run this command.

```
jekyll new myawesomeblog
```

What this command does is call the `jekyll` command. `new` tells the Jekyll command that you want to create a new Jekyll project in the current folder. That Jekyll project should be created in a folder called `myawesomeblog`.

To see your new Jekyll site in action, go into your project folder by typing in `cd myawesomeblog` in your Terminal, replacing `myawesomeblog` with whatever you named your Jekyll project.

Then type in `jekyll serve` in your Terminal window. Running this command will start a server on your machine so that you can see what your Jekyll site will look like once it is generated.
<div style="page-break-after:always;"></div>
The final two lines of output once you're running the Jekyll server should be something like this.

```
Server address: http://127.0.0.1:4000/
Server running... press ctrl-c to stop.
```

You can open up a browser window and type in `http://127.0.0.1:4000` into your URL bar. Alternatively you could type in `http://localhost:4000` as well and it will also point to your Jekyll server. To stop the server, simply press the *control* key and the *c* key on your keyboard.

# Conclusion

Congrats! If you've made it to this point, you have Jekyll up and running on your system and ready to build some awesome websites. Discovering Jekyll has saved me a ton of time and heartache when it comes to building websites and I hope the same results for you.

I'd love to connect with you. If you're on Twitter, be sure to follow me at [@michaelsoolee](https://twitter.com/michaelsoolee). If you've got any comments or questions feel free to shoot me an email at [michaelsoolee@gmail.com](mailto:michaelsoolee@gmail.com).

Thanks and cheers!

Michael Lee<br>
[michaelsoolee.com](https://michaelsoolee.com)
