+++
date = '2025-02-14T20:01:12+08:00'
draft = false
title = 'Why Nimpylib'
weight = 1
+++


It helps you to:
- use much Python-like out-of-box API in Nim:
  - with no need of any Python dependency (neither dynamic library nor binary).
  - even handy for ones who don't use much Python but want more functions in Nim
- translate your Python program to Nim:
  - gaining a right-away speed boot of even 700x
  - no worry about binary distribution or packaging, just "compile once, distribute everywhere"
  - amazing small binary size: as of v0.9.7, for a simple `print("hello world")`,
    the produced binary is only:
    - 372K in debug
    - 176K in release
    - even 56K with size strip compile flags like `-d:strip`[^reduce]
    on MacOS.
  - rid of many annoying runtime-errors (which are turned to compile-time error)
- gain a better view into different behaviors between Python and Nim:
  - `dynamically-typed` vs `statically-typed`
  - unconvertible syntax from Python to Nim, e.g.
    [`end` keyword]({{<repo-url "doc/mustRewriteExtern/endKeyword.md" >}}),
    [`not in` syntax]({{<repo-url "doc/mustRewriteExtern/not-in.md" >}})

[^reduce]:  consider flag of ` -d:danger -d:strip --opt:size --threads:off -x:off -t:-flto ` (if gcc/clang is used),
  which reduces size to even 55.6K

...


> Copied from [repo's README.md](
  {{< repo-url commit="34b29a95892c5652ade1794ff92b7363e5830d59"
  path="README.md#why-nimpylib" >}})
but update link of [mustRewriteExtern]({{<repo-url "tree" "mustRewriteExtern/">}})
