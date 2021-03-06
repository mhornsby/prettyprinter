# 1.2.1

- Add function to trim trailing space in layouted `SimpleDocStream`,
  `removeTrailingWhitespace`
- Add `Pretty` instances for `Identity` and `Const`

# 1.2.0.1

- Fix `alterAnnotationsS` (and thus `unAnnotateS`), which removed pushing, but
  not popping, style frames. This led to them throwing errors in pretty much all
  use cases.

# 1.2

- `encloseSep` does no longer include an `align` wrapper; in other words,

    ```haskell
    encloseSep_old … = align (encloseSep_new …)
    ```
- Change the default ribbon fraction to 1 (was 0.4)
- Expose `viaShow` and `unsafeViaShow` from the public module
- Fix `layoutSmart` behaving as if there was no space left for unbounded pages

# 1.1.1

- Add `panicPeekedEmpty` and `panicPoppedEmpty` to the panic module

# 1.1.0.1

- Rendering directly to a handle is now more efficient in the `Text` renderer,
  since no intermediate `Text` is generated anymore.
- Remove upper version bounds from `.cabal` files

# 1.1

- Allow `alterAnnotations` to convert one annotation to multiple ones, to
  support e.g. `Keyword ---> Green+Bold`
- Remove `Pretty` instance for `Doc`: the implicit un-annotation done by it did
  more harm than good.

# 1.0.1

- Add `alterAnnotations`, which allows changing or removing annotations.
  `reAnnotate` and `unAnnotate` are now special cases of this.
- Fix »group« potentially taking exponential time, by making the (internal)
  `flatten` function detect whether it is going to have any effect inside
  `group`.
- Add proper version bounds for all dependencies and backport them to version 1
- Haddock: example for `Pretty Void`

# 1

- Add Foldable/Traversable instances for `SimpleDocTree`, `SimpleDocStream`
- Add Functor instances for `Doc`, `SimpleDocTree`, `SimpleDocStream`
- Add the simplified renderers `renderSimplyDecorated` and
  `renderSimplyDecoratedA` to the tree and stack renderer modules
- Lots of typo fixes and doc tweaks
- Add a changelog :-)

# 0.1

Initial release.
