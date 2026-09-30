# Clean Code Principles & Rules

## Core principles
- Readability first: code is read far more than written; optimize for the next reader
- KISS: choose the simplest solution that works
- YAGNI: don't build for hypothetical future needs
- DRY after the third repetition, not the first; duplication is cheaper than the wrong abstraction
- Boy Scout Rule: leave touched code slightly cleaner, but don't refactor unrelated code
- Single Responsibility at every level: function, class, module

## Naming
- Names reveal intent: say what it is or does, not how
- Use pronounceable, searchable names; no cryptic abbreviations (`usr`, `tmp`, `data2`)
- Booleans read as questions (`isActive`, `hasAccess`); functions are verbs, types are nouns
- One word per concept across the codebase (don't mix `fetch`/`get`/`retrieve`)
- Avoid noise words (`Manager`, `Helper`, `Util`, `Info`) and type-encoding prefixes
- Name length proportional to scope: short in tiny scopes, descriptive in wide ones

## Functions
- Small and do one thing; one level of abstraction per function
- Max ~3 parameters; group more into an object
- No boolean flag arguments; split into two functions
- Avoid side effects and hidden state changes; separate commands from queries
- Prefer pure functions for logic
- Return early with guard clauses; avoid nesting deeper than 2-3 levels
- No output parameters; return values instead

## Comments
- Code should explain itself; comment the *why*, never the *what*
- Delete commented-out code (git remembers it)
- No stale, redundant, or noisy comments
- TODOs must be actionable and tracked; don't leave them to rot

## Formatting & structure
- Follow the project formatter/linter; don't debate style manually
- Keep related code close; declare variables near first use
- Order top-down: high-level first, details below
- Keep files and classes small and cohesive
- Avoid magic numbers and strings; use named constants or enums

## Error handling
- Fail fast; validate inputs at the boundary
- Use exceptions/typed errors, not error codes or `null` returns
- Never swallow errors silently; handle or propagate with context
- Error messages state what happened and how to act
- Don't use exceptions for normal control flow

## Design
- Low coupling, high cohesion
- Depend on abstractions; inject dependencies
- Law of Demeter: avoid long call chains
- Prefer composition over inheritance
- Make illegal states unrepresentable; prefer immutability
- Avoid global mutable state

## Testing
- Tests are first-class code: same readability standards apply
- One behavior per test; descriptive names (`returns_error_when_email_invalid`)
- Fast, independent, repeatable, self-validating
- Follow Arrange-Act-Assert; no logic in tests
- Test behavior, not implementation details

## Code smells to avoid
- Long functions or parameter lists, god classes
- Deep nesting, duplicated logic, dead code
- Shotgun surgery (one change touches many files)
- Feature envy (method uses another class's data more than its own)
- Primitive obsession (use value objects for domain concepts)
- Speculative generality and premature optimization

## Working rules
- Make the change minimal and focused; no drive-by refactors
- Match existing conventions of the codebase over personal preference
- Refactor only with passing tests; make behavior-preserving steps small
- Measure before optimizing; correctness and clarity come before speed
