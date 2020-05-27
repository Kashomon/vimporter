# Vimporter

Vimporter is a thought experiment.

The goal is to provide functionality to build static-plugins with Vim. To be
more precise, goal is for Vim plugins to depend on other plugins, without
needing the user to actually install those other plugins as shared libraries.

## How it works

A plugin specifies a `requirements.vim.txt` file, which can be used by
Vimporter, itself a Vim plugin.

## Installing

With Vundle:

```
Plugin 'Kashomon/vimporter`
```

## requirements.vim.txt

```
namespace: example
requirements:
- google/vim-maktaba >= 0.15.0
- zorp >= 0.1.0
```

Opening `requirements.vim.txt` in Vim and running `:Vimporter import` clones
the plugins' autoload directories and renames them appropriately.

Note: I've used YAML here for the format.

## Analysis

* Makes it easier to copy-and-paste plugin code
* Can't really do interesting dependency analysis: would need to copy the wole
  plugins.
