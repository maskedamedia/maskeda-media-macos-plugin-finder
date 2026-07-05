# Repository Instructions

## Portable development standards

<!-- portable-agents-baseline:v1 -->

These standards travel with the repository. Project-specific guidance elsewhere
in this file remains authoritative when it is more specific or stricter.

### Project context

- Read `README.md`, `AGENTS.md`, relevant documentation, configuration, CI, and
  package files before changing code.
- Understand the repository's purpose and established conventions before
  proposing structural changes.
- Prefer existing project patterns, tools, naming, and architecture.
- Avoid unrelated cleanup or refactoring.

### Git safety

- Preserve all existing work.
- Never reset, clean, discard, overwrite, force-push, rewrite history, delete
  branches, or remove files without explicit approval.
- Inspect Git status, the current branch, remotes, upstream tracking, and
  pending changes before editing.
- Do not commit, push, merge, tag, publish, or deploy without explicit approval
  unless the current task explicitly authorizes those actions.

### Branch workflow

Each feature branch represents a milestone-sized project goal.

Use `milestone/short-description-YYYYMMDDHHMMSS`, for example
`milestone/add-license-management-20260704221530`.

- Use lowercase, a hyphen-separated description, and a
  `YYYYMMDDHHMMSS` timestamp.
- Merge into the repository's established stable or default branch after
  validation; do not assume that branch is always `main`.
- Document the milestone purpose and acceptance criteria.

### Version and build identifiers

- Prefer `YYYYMMDDHHMMSS` for build, artifact, milestone, and internal-release
  identifiers.
- Preserve semantic versioning where existing conventions, package managers,
  app stores, APIs, or public release contracts require it.
- When semantic versioning is required, use timestamps as build metadata,
  release metadata, CI build numbers, or artifact identifiers.

### Documentation

Documentation is part of implementation.

- Update or propose documentation when changing setup, commands, dependencies,
  architecture, workflows, environment-variable names, deployment, recovery,
  troubleshooting, or public interfaces.
- Create or update an appropriate Markdown file when implementing a new
  process.
- Apply the 3x rule: if a task is repeated three or more times, propose
  automation, documentation, or a reusable tool.

### Root README Markdown index

Every repository must have a root `README.md` that links to every other
top-level Markdown file.

- Use relative links and alphabetize the Markdown document list.
- Include `AGENTS.md` and exclude `README.md` itself.
- Exclude generated, vendored, dependency, hidden-directory, and build-output
  documentation.
- Keep the index updated when top-level Markdown files are added, renamed, or
  removed.
- Preserve the existing README structure. Add or update a clearly labeled
  documentation section instead of rewriting the file unnecessarily.

### Code quality

- Run applicable existing formatting, lint, syntax, type, unit, integration,
  build, dependency-vulnerability, static-security, and accidental-secret
  checks for code changes.
- Use repository-defined package scripts, Make targets, task runners, CI
  commands, lockfiles, and documented commands first.
- Do not introduce a competing formatter, linter, package manager, test
  framework, or scanner without a clear reason.
- Do not automatically fix unrelated findings.
- If checks cannot run, report what failed, why, the missing dependency or
  credential, and the exact command to run later.

### Tooling

Before installing anything:

1. Check whether the tool already exists.
2. Check runtime managers and project-local environments.
3. Inspect repository documentation and lockfiles.
4. Prefer project-local dependencies.
5. Avoid duplicate or unnecessary global installations.
6. Before a system-wide installation, report the package, version, source,
   scope, disk impact, and reason.

Do not perform broad global upgrades without explicit approval.

### Credentials and secrets

- Never print, expose, log, summarize, commit, or transmit secrets.
- Never place credentials in documentation.
- Use environment-variable names in documentation, never values.
- Prefer existing authenticated sessions, SSH configuration, credential
  helpers, and environment-provided tokens.
- Do not initiate a new login flow when a valid existing credential is
  available.
- Never alter credential stores, private keys, or authentication scope without
  explicit approval.

### Completion reporting

At the end of substantial work, report:

- Completed
- Validation performed
- Remaining work
- Blockers
- Automation opportunities
- Technical debt
- Documentation updated
- Approval-required actions
