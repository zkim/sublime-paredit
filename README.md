# Paredit mode for Sublime Text 2!
## An Emacs-style Paredit mode that gets strict about closing parentheses and helps you nest parentheses

This is a simple plugin, very much in beta, that attempts to emulate Emacs' Paredit, which enforces matched parentheses, among other things. While Sublime has default bracket matching, it's not strict about it. The goal is make writing Lisp variants (like Clojure, Scheme, Common Lisp, etc.) not so awful in Sublime.

## Installation

First, make sure you've installed Sublime's package manager, [Package Control](http://wbond.net/sublime_packages/package_control/installation).

Until I've finished adding Windows and Linux keymappings, this isn't in Sublime's Package Control. In the mean time, you can simple use Sublime's Package Control: Add Repository command and add `https://github.com/masondesu/sublime-paredit` as a repo. Then searching for 'paredit' in Package Control: Install Package will show this package.

## Usage
Once the package is installed, you'll see Paredit Mode under the Tools Menu. 

![](http://f.cl.ly/items/3N3g0a140k2F2Y302Q34/1o.png)

When toggled, parentheses will *always* close. In otherwords,
* Whenever you type `(`, a `)` will automatically be inserted after it, or after the selected text.
* You can't delete the opening or closing parenthesis of a matched set that contains anything other than nothing, or whitespace.
* You *can* force delete any parenthesis with `shift+delete`.

Also, when inside of a matched set, pressing `cmd + )` (a.k.a. `cmd + shift + 0`) will emulate Emacs and "push" the matched closing bracket beyond the next matched set on the same nesting level. Using this hotkey would turn this

```scheme
(foo)(bar (baz))
```
into this
```scheme
(foo (bar (baz)))
```

... which is rather handy.

## Contributing
I'm not much of a Python hacker, as you can clearly see by looking as the source. I hacked this together over a couple of sessions, but there is lots of room for improvement. Open a Pull Request and I'll gladly take a look.

### License
This project is licensed under The MIT License (MIT). See LICENSE for more details.
