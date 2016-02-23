# fltkhs-demos

These are end-to-end demos of [FLTKHS] [1], a Haskell Binding to the FLTK GUI Library


Fltkhs-demos aims not only to show off the features of the [fltkhs] [1] but also
serve as a way of learning the API by example. For more thorough documentation
on the [fltkhs] [1] API please see the [FLTKHS module] [2] of that package.

## Introduction

The demos shipped with this package are listed in `fltkhs-demos.cabal` as
separate `Executable` components. Once the package is installed they are
installed to a location known to Stack, so to execute `fltkhs-arc` for instance
do:

```
> stack exec fltkhs-arc
```

Note that all the executables are prefixed with \"fltkhs-\". This is in order to
prevent the demo executables from stomping over applications of the same name
the user might already have installed. Typing:

```
 > fltkhs-<TAB>
```

at the command line should show a complete list of available demos.

## Learning The API

Most of the demos are exact ports of those shipped in the 'test' directory of
the <http://fltk.org FLTK> distribution. It is hoped the user will study the
Haskell demo code side-by-side with the C++ demo code in order to understand the
API. The section __API Guide__ in the [FLKTHS documentation] [2] covers this in more detail.

## Why is the demo code so un-Haskelly?
For being written in Haskell, the demo code is horrifyingly/amazingly imperative and stateful. Although it may repulse those
who used to pure Haskell idioms it is that way for a reason.

The demo code was never meant to be idiomatic Haskell code but a way of showing as much of the API as possible. The API itself
closely resembles the underlying C++ code which is imperative and stateful. This has the advantage of making the API easier
to learn.

For instance, assuming FLTK was installed from source compare /src/Examples/arc.hs with /test/arc.cxx in the FLTK
source directory. There is quite a bit of correspondence and it is easy to see how the Haskell API functions map to the C++ ones.

## Fast Compilation Flag

This package comes with a flag `fastCompile` that is enabled by default and speeds up compilation. More information on this flag is available under the __Compilation__ section of the [FLTKHS documentation] [2].

To disable this flag, tell Stack to ignore it during the `configure` step:

```
stack build --flag fltkhs-demos:-fastCompile
```

# GHCi

Please see "Running In The Repl" [5] section of the FLTKHS documentation for more information.


  [1]: http://hackage.haskell.org/package/fltkhs/
  [2]: http://hackage.haskell.org/package/fltkhs/docs/Graphics-UI-FLTK-LowLevel-FLTKHS.html
  [3]: https://github.com/deech/fltkhs-fluid-hello-world
  [4]: https://ghc.haskell.org/trac/ghc/ticket/10568
  [5]: http://hackage.haskell.org/package/fltkhs/docs/Graphics-UI-FLTK-LowLevel-FLTKHS.html#g:14