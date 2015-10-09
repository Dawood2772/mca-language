# Roadmap

## Standard API
 - [ ] **Documentation!**
 - [ ] Synchronous file I/O API
 - [ ] Reflection API

## Language
 - [x] Documentation
   - Initial version complete, but not comprehensive yet
 - [x] Closures
 - [ ] Make blocks in control statements create scopes (similar to `let` in JS)
 - [ ] Add a `var` keyword
 - [ ] Branchable blocks and macros (i.e MCIL branching support)
 - [ ] `@` player references in expressions, supporting parameters
   - Supports binary operations (e.g. `@p | @r` would select the nearest player as well as a random player, `@p & @r` would select the nearest player if they are the random player)
   - Casting to a string results in the selector as it would appear in a command
 - [ ] Explicit casting (e.g. `(string)0.12`)
 - [ ] Some way to get compile arguments (i.e argv)
 - [ ] Try/catch support
 - [ ] Named parameters (as a result, supporting multiple overloaded macros with the same number of parameters, but different argument names)
   - If two macros have the same number of parameters and not enough names are provided to decide which to use, throw an `ArityError` or similar
 - [ ] Multiple return values
