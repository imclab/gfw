# What is Global Forest Watch?

[Global Forest Watch](http://www.globalforestwatch.org/) (GFW) is a dynamic online forest monitoring and alert system that empowers people everywhere to better manage forests.

This repository contains the GFW web app.

![](http://i.imgur.com/JnVtiHU.png)

# Developing

The GFW web app rides on [Ruby on Rails](http://rubyonrails.org).

## OS X Mavericks Setup

First make sure you have [Xcode](https://developer.apple.com/xcode) and [Command Line Tools](https://developer.apple.com/downloads/index.action) installed.

Next install [Homebrew](http://brew.sh), the OS X package manager:

```bash
$ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"
```

We recommend managing your Ruby installation through [rbenv](https://github.com/sstephenson/rbenv). It's just an easy way to run multiple Ruby versions for different applications:

```bash
$ brew update
$ brew upgrade rbenv ruby-build
```

Next clone the gfw repo:

```bash
$ git clone https://github.com/Vizzuality/gfw.git
```

Using rbenv, install and set Ruby 2.1.1 in the main app directory:

```bash
$ cd gfw
$ rbenv install 2.1.1
$ rbenv local 2.1.1
```

Now let's install Ruby on Rails:

```bash
$ sudo gem install rails
```

Aaaaand now use [Bundler](http://bundler.io/), a rubygem manager, to install all the gem depenencies for the app:

```bash
$ bundle install
```

Almost there! Final steps are to update your `.env` file:

```bash
RACK_ENV=development
GFW_API_HOST=gfw-apis.appspot.com
BLOG_HOST=http://blog.globalforestwatch.org
AWS_HOST=
TERMS_COOKIE=
S3_BUCKET_NAME=
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
```

Last step. For real. Start the app server and access it at [http://0.0.0.0:5000](http://0.0.0.0:5000):

```bash
$ foreman start
```

Oh, and you should probably launch the [gfw-api](https://github.com/wri/gfw-api) [dev_apperver.py](https://github.com/wri/gfw-api#developing) before you try to visit the site on your local machine.

# License

The MIT License (MIT)

Copyright (c) 2014 Vizzuality

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
