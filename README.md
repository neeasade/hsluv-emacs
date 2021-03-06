# hsluv-emacs

## Introduction

This package provides an Elisp implementation of the HSLUV colorspace
conversions as created by Alexei Boronine (@boronine), and documented on
http://www.hsluv.org/

HSLuv is a human-friendly alternative to HSL.

CIELUV is a color space designed for perceptual uniformity based on human
experiments. When accessed by polar coordinates, it becomes functionally
similar to HSL with a single problem: its chroma component doesn't fit into
a specific range.

HSLuv extends CIELUV with a new saturation component that allows you to span
all the available chroma as a neat percentage.

The reference implementation is written in Haxe and released under
the MIT license. It can be found at https://github.com/hsluv/hsluv
The math is available under the public domain.

## Installation

The recommended way is to use [MELPA](http://melpa.org/). If either is in your `package-archives`, do

    M-x package-install RET hsluv RET

or you could use something like [use-package](https://github.com/jwiegley/use-package):

```elisp
(use-package hsluv)
```

No further configuration is needed.


## Using

The following functions provide the conversions
from RGB to/from HSLUV and HPLUV:

```elisp
(hsluv-hsluv-to-rgb (list H S Luv))

(hsluv-hpluv-to-rgb (list H P Luv))

(hsluv-rgb-to-hsluv (list R G B))

(hsluv-rgb-to-hpluv (list R G B))
```

## Testing

If you want to run the tests, checkout this repository. Then, on a command-line near you, do:

```sh
$ make clean test
```

which will run the tests defined in `test/hsluv-test.el`.

Test results will be collected in the file `test-results.log`
