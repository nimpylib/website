+++
date = '2025-12-19T09:57:46+08:00'
draft = false
title = 'Pylib Integration Project'
+++

# NPython & NimPyLib Integration Project

## Motivation
It has been a long time since I planned to split the pylib monorepo into several,
so that other libaries like npython can use functions of its
without `requires` the whole nimpylib (which is too big).

And as more and more snippets were copied from pylib to npython,
it's high time that we should use nimble `requires` instead of ^C & ^V (or yy & p)


## Started
Today the first step eventually is set out: [pyrepr][] is moved from three parts of pylib

## Further

For scheduled integration, refer to [nimpylib project #4](https://github.com/orgs/nimpylib/projects/4)


[pyrepr]: https://github.com/nimpylib/pyrepr


