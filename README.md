# linter-rubocop

[![Gitter](https://img.shields.io/badge/gitter-join%20chat-1dce73.svg?style=flat)](https://gitter.im/AtomLinter/Linter?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://travis-ci.org/AtomLinter/linter-rubocop.svg?branch=master)](https://travis-ci.org/AtomLinter/linter-rubocop)
[![Plugin installs!](https://img.shields.io/apm/dm/linter-rubocop.svg)](https://atom.io/packages/linter-rubocop)
[![Package version!](https://img.shields.io/apm/v/linter-rubocop.svg?style=flat)](https://atom.io/packages/linter-rubocop)
[![Dependencies!](https://david-dm.org/AtomLinter/Linter.svg)](https://david-dm.org/AtomLinter/linter-rubocop)

This linter plugin for [Linter](https://github.com/AtomLinter/Linter) provides
an interface to [rubocop](https://github.com/bbatsov/rubocop). It will be used
with files that have the “Ruby” syntax.

## Installation

Linter package must be installed in order to use this plugin. If Linter is not
installed, please follow the instructions [here](https://github.com/AtomLinter/Linter).

### `rubocop` installation

Before using this plugin, you must ensure that `rubocop`, version 0.37 or
greater, is installed on your system. To install `rubocop`, do the following:

1.  Install [ruby](https://www.ruby-lang.org/).

2.  Install [rubocop](https://github.com/bbatsov/rubocop) by typing the
    following in a terminal:

    ```shell
    gem install rubocop
    ```

Now you can proceed to install the linter-rubocop plugin.

### Plugin installation

```shell
apm install linter-rubocop
```

## Settings

You can configure linter-rubocop by editing `~/.atom/config.cson`
(choose Open Your Config in Atom menu):

### Using RVM

If you're using RVM and receiving errors in Atom that indicate Rubocop can't be
found, you may need to change `/bin` to `/wrappers` in the path that gets
returned from `which rubocop` before using it as your `command` setting.
For example, change:

```cson
"linter-rubocop":
  command: "/Users/JohnDoe/.rvm/gems/ruby-2.2.4@global/bin/rubocop"
```

To:

```cson
"linter-rubocop":
  command: "/Users/JohnDoe/.rvm/gems/ruby-2.2.4@global/wrappers/rubocop"
```
### Using `rbenv`

If you're using `rbenv`, it's recommended that you set your `command` to point to the Rubocop shim. This way, when you upgrade Ruby, the command will be a pointer to a Rubocop executable, regardless of your current Ruby version.

```cson
"linter-rubocop":
  command: "/Users/JohnDoe/.rbenv/shims/rubocop"
```

### Using `chruby`

If you're using `chruby `, it's recommended that you set your `command` to execute `chruby-exec` to set version and run `rubocop`. Alternatively, you can reference the full intended path.

```cson
"linter-rubocop":
  command: "/usr/local/bin/chruby-exec 2.5.0 -- rubocop"
```

or

```cson
"linter-rubocop":
  command: "/Users/JohnDoe/.gem/ruby/2.5.1/bin/rubocop"
```
