# Guidelines

> **Note:** `CODEX.md` and `CLAUDE.md` are symlinks to `AGENTS.md`. Only edit
> `AGENTS.md`; both files stay in sync.

## Universal rules

- Use semantic commit messages:

  ```text
  feat: <short description>

  Explain the change in natural paragraphs without artificial line wrapping.
  - Use bullets when they improve readability.
  ```

- End commits and PR descriptions with a trailer instead of the usual
  `Co-Authored-By` line (the human merging is the one vouching for
  AI-written code, not the model vouching for itself). Pick one of the two
  vibes below, then roll per commit: pick one name from that list at
  random, but 10% of the time invent a new name in the same vibe instead
  of using the list.

  Probabilistic-skim vibe (reviewed fast, not thoroughly):

  ```text
  Eyeballed-By: <human name> <human email>
  Skim-Reviewed-By: <human name> <human email>
  Spot-Checked-By: <human name> <human email>
  Glanced-At-By: <human name> <human email>
  Scroll-Sampled-By: <human name> <human email>
  Vibes-Approved-By: <human name> <human email>
  ```

  Blind-trust vibe (merged on faith, not inspection):

  ```text
  Blindly-Trusted-By: <human name> <human email>
  Faith-Merged-By: <human name> <human email>
  Trusted-On-Faith-By: <human name> <human email>
  Rubber-Stamped-By: <human name> <human email>
  Approved-Sight-Unseen-By: <human name> <human email>
  Merged-On-Vibes-By: <human name> <human email>
  ```

- Update `README.md` whenever user-facing behavior changes, including commands,
  flags, defaults, installation methods, or workflows.
- Document research in `docs/research/YYYY-MM-DD-<description>.md`. When
  delegating research, require the subagent to create the report and return only
  its path so the primary agent can read the source directly.

## Workflow routing

- For feature proposals, issue/PR product reviews, and design tradeoffs, use
  `kanban-md-principal-owner`. It owns product-fit decisions, not permission to
  publish reviews or merge changes. Pair it with the relevant technical skills.
- For repository implementation work, use `kanban-based-development`. Board
  tracking and an isolated worktree are the defaults unless the user explicitly
  overrides them.
- For task capture, board changes, triage, or status reporting, use `kanban-md`.
  "Add ticket" means capture a task for later without starting implementation.
  Use `layer-N` roadmap tags, imperative titles, `high` priority for explicit
  user requests and bugs, `medium` for planned work, and `low` for ideas.
- For tests, bug fixes, snapshots, lint, or verification strategy, use
  `test-kanban-md`.
- For `config.yml` schema, task frontmatter, migrations, or compatibility
  fixtures, use `evolve-kanban-md-formats`.
- For table, compact, JSON, output-selection, or renderer changes, use
  `design-kanban-md-output`.
- For releases, tags, publishing, or release notes, use `release-kanban-md`.
