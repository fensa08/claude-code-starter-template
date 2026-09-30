Think of CLAUDE.md as a note you'd leave a smart new teammate on day one. Not a manual, just the stuff they couldn't guess.

What to put in

How to build, test, lint, and run the thing (exact commands)
A quick map of the codebase: what lives where and why
Conventions that aren't obvious from the code ("we use Zod for validation, never raw types at API boundaries")
Gotchas and landmines ("don't touch the migrations folder by hand")

What to leave out

Anything Claude can figure out by reading the code
Rules your linter or formatter already enforces
Long docs, since link or @import them instead
Vague advice like "write clean code"
Secrets, ever

Habits that help

Keep it short. It's loaded every session, so every line costs context. If it's growing past a couple hundred lines, split into .claude/rules/ files or imports.
Be specific and direct. "Run npm test -- --watch=false before finishing" beats "make sure tests pass."
Grow it from mistakes. When Claude gets something wrong twice, add one line. When a line stops mattering, delete it.
Layer it. Global preferences in ~/.claude/CLAUDE.md, project rules in the repo root, and nested CLAUDE.md files in subfolders for local quirks.
Commit it. The team shares it, and it improves with everyone's input.
Use hooks for must-happen rules. CLAUDE.md is guidance, and Claude can occasionally miss it. If something must never be skipped (formatting, blocking .env edits), enforce it with a hook.

A quick test: if you removed a line and Claude would behave the same, cut it.

20/80 Princple; 

Put the commands in first. Build, test, lint, run, typecheck, exactly as you'd type them. This one section fixes most "Claude did it wrong" moments.
Add a 5-10 line architecture map. What the main folders are, where the entry points live, and how the pieces connect. It saves Claude from wandering around your repo every session.
Write down your non-obvious rules. Only the conventions you'd correct in a code review, like "always use the repo's logger, never console.log" or "all DB access goes through the repositories/ layer."
Add a "don't touch" list. Generated files, migrations, vendored code, anything fragile. It's cheap insurance against costly mistakes.
Tell Claude how to verify its work. "Run npm test and tsc --noEmit before saying you're done." A verification loop matters more than any style rule.
Start tiny and grow from mistakes. Don't try to write the perfect file upfront. Every time Claude repeats an error, add one line. After a few weeks you'll have a file that's tuned to your actual problems.
Prune ruthlessly. If a line wouldn't change Claude's behavior, delete it. A short file gets followed, and a bloated one gets diluted.
Move the must-happen stuff to hooks. Formatting, blocking risky edits, running tests. CLAUDE.md is advice, and hooks are enforcement.