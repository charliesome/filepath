# filepath
### `which` for open files

Do you drag file handles from app titlebars into your terminal a lot?
And you consider yourself a hardened keyboard warrior and don't like
using the mouse unless absolutely necessary?

## Without `filepath`

(These following screenshots are out of date and reflect v0.2)

![Without filepath](https://img.skitch.com/20110421-x5476hjstjuf74wpyg83h763a2.png Without filepath)

Sure, you might say "I'd just type and tab complete that shit." But let's
just imagine that file is really deep in the project hierarchy
or just really damn annoying to autocomplete because there's a billion
files with the same prefixes.

Now, let's take a look at your coding life with `filepath`.

## With `filepath`

![With filepath](https://img.skitch.com/20110421-q1msk7rux2xcjbdm2r5uq6j1i.png With filepath)

"Holy shit, that's amazing!" you say, "But what about if I have more
than one window? Which one does it choose?"

![Choices](https://img.skitch.com/20110421-k1ud63xtwprwgi8c7pjsb1wgsb.png choices)

You get a choice! `filepath` is democratic like that.

## Want it?

You can grab it from the [downloads page](https://github.com/chendo/filepath/downloads)
or build it yourself, then slap it in any directory in your $PATH (I
suggest `/usr/local/bin`).

I'll probably write a recipe for homebrew at some point.

This requires Snow Leopard (10.6) and access for assistive devices must
be enabled in Accessibility.

This only works on applications that use NSDocument. Let me know if it
doesn't work for an application with a draggable handle in the title bar.

If you somehow don't have Snow Leopard, upgrade already.

## Basic Usage (which there's not much point to)

    $ filepath                # Gets the path from the most recently used window
                              # that has a document
    /Users/chendo/foo.txt

    $ filepath textmate       # Gets documents from Textmate
    /Users/chendo/opened_in_textmate.txt

    $ filepath --verbose
    Getting path from MacVim...
    /Users/chendo/foo.txt

    $ filepath --choose       # Gives you the option to pick which file to
                              # output to stdout
    Multiple paths found:
    1: /Users/chendo/foo.txt
    2: /Users/chendo/bar.txt
    Enter choice: 2
    /Users/chendo/bar.txt

## Intended Usage

    $ alias fp=filepath       # For the lazy
    $ cucumber `fp`
    $ spec `fp`
    $ git add `fp`

And so on and so forth. If you use `zsh`, then you can do:

    $ cucumber `fp`<TAB>      # And zsh will replace `fp` with the actual path and becomes:
    $ cucumber /Users/chendo/awesome.feature

## Why?

I like being efficient. I'd rather spend an hour or two writing a tool
making me more efficient in the long run than waste two seconds every
time I drag a file into the terminal.


## Changelog

* v0.3
  * Now using getopt_long for option parsing goodness
  * Silenced the output by default to make it more zsh backtick
    subsitution-friendly.
  * Added --verbose
  * Picks the first file by default unless --choose is selected
  * Added Usage and help

* v0.2
  * Added -f option.

* v0.1
  * First release.

## Contribute

Fork and send me pull requests! You might be able to tell that I don't
code Objective-C/C very often and so I'm happy to learn better ways of
doing things.

## License

(The MIT License)

Copyright © 2011 Jack "chendo" Chen

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the ‘Software’), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED ‘AS IS’, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

