# Pest.rs Grammar for Lua Syntax

This is a work in progress. And is incomplete.

## Lua 5.4 PEST Grammar

This is my attempt build a non-toy grammar in [Pest.rs](https://pest.rs) for Lua 5.4.

I started by trying to port over the [Lua 5.4 Syntax in EBNF](https://www.lua.org/manual/5.4/manual.html#9)
from the Lua Manual to PEST.  It turns out there are three things missing from that syntax:

1. LiteralString: e.g. `"a string\n"`
2. Name: `[a-zA-Z_][a-zA-Z_]+`
3. Numeral

Turns out there's a bunch of fucking number formats.
More information in the Lua [5.4 Manual Section 3.1](https://www.lua.org/manual/5.4/manual.html#3.1)

## Status

This is not under active development.
It was a learning project which I may or may not continue work on.
If you'd like to contribute I'm happy to accept PRs.

## Incomplete

- [ ] Try Implicit Whitespace [Docs](https://pest.rs/book/grammars/syntax.html#implicit-whitespace)
again. Currently has explicit "X" (mandatory whitespace) and "W" (optional whitespace) everwhere.
- [ ] Get multi-line properly working
- [ ] Rust code to use this grammar
    - [ ] Implement PrattParser
    - [ ] Recursive rules
    - [ ] [Operator Precedence](https://pest.rs/book/precedence.html)
- [ ] Add Lua keywords as exclusions from Name (function, end, loop, etc)
- [ ] Build test rig
- [ ] Test against existing test suites

And much more.

## See also:

* [Lua ANTLR4 Grammar](https://github.com/antlr/grammars-v4/blob/master/lua/Lua.g4)
* [Roblox Luau EBNF Grammar](https://github.com/Roblox/luau/blob/master/docs/_pages/grammar.md)
* [Wikipedia Extended Backus–Naur form (EBNF)](https://en.wikipedia.org/wiki/Extended_Backus%E2%80%93Naur_form)

## Copyright / License

Copyright (c) 2023 Peter Tripp. Apache 2.0 License.
