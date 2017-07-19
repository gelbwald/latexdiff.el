# Emacs-latexdiff

## Introduction
latexdiff is a minor mode to interact with [Latexdiff]
(https://github.com/ftilmann/latexdiff) for version controlled
repositories.

## Requirements
Emacs-latexdiff require Emacs-24.3 or later versions
and optionnaly [Helm](https://github.com/emacs-helm/helm)

# Getting started

## Install latexdiff
Install `latexdiff` from your package manager or from
[the official website](https://github.com/ftilmann/latexdiff).
Emacs-latexdiff use `latexdiff-vc' so make sure it is available.

## Install Emacs-latexdiff from git
  1. Clone the `latexdiff` repository to some directory:

    ```bash
    $ git clone https://github.com/muahah/latexdiff.git /path/to/latexdiff/directory
    ```

  2. Add to `.emacs.el` (or equivalent):

    ```elisp
    (add-to-list 'load-path "/path/to/latexdiff/directory")
    (require 'latexdiff)
    ```

## Install Emacs-latexdiff from MELPA
```elisp
(package-install 'emacs-latexdiff)
```

## Configuration
Emacs-latexdiff faces and behaviour can be customized through the customization panel :
```elisp
(customize-group 'latexdiff)
```

Emacs-latexdiff do not define default keybinding, so you may need to add
them :
```elisp
(define-key latex-mode-map (kbd "C-c l d") 'helm-latexdiff)
```
or for Evi users:

```elisp
(evil-leader/set-key-for-mode 'latex-mode "ld" 'helm-latexdiff)
```

## Basic usage

 - `latexdiff` will ask for two tex files and generates a pdf diff between them, this is the only function that work outside of a repository.
 - `latexdiff-vc` (and `helm-latexdiff-vc`) will ask for a previous commit number and make a pdf diff between this version and the current one.
 - `latexdiff-vc-range` (and `helm-latexdiff-vc-range` will ask for two commits number and make a pdf diff between those two versions.
 - `helm-clean` allow to remove **All** file generated by latexdiff (pdf included)

# Contributing
The project is hosted on [github](https://github.com/galaunay/emacs-latexdiff).
To contribute, install Cask and then:
```bash
$ make install
```

Run the tests with:
```bash
$ make test
```
