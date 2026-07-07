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

## maskeda media operating standards

<!-- maskeda-operating-standards:v1 -->

These standards capture recurring operating requirements for maskeda media
repositories. They are portable repository guidance; host-specific paths,
machine names, credentials, and local-only assumptions belong in host-level
instructions, not here.

### Brand writing

- Write the brand as `maskeda media` in normal prose, headings, titles,
  metadata, and structured data.
- Use `MASKEDA MEDIA` only when an explicitly all-caps visual treatment is
  required.
- Do not write `Maskeda Media` unless preserving an existing external proper
  name, repository name, legal text, or direct quote that must remain unchanged.

### Environment and workspace boundaries

- Respect the operating context documented by the host or project before
  changing files, services, paths, or tools.
- Do not assume that paths, services, ports, credentials, browser sessions, or
  filesystem views are identical across operating systems, containers, virtual
  machines, remote hosts, or development environments.
- State which environment is being inspected or changed when the distinction
  matters.
- Keep host-specific paths, usernames, machine names, installed-tool paths, and
  local-only assumptions out of repository documentation unless this repository
  explicitly exists to document that host or environment.

### Safe configuration and secret inspection

- Never print, paste, quote, summarize, or include raw `.env`, credential,
  token, private-key, recovery-code, database-url, cookie, session, or other
  secret-bearing file contents in chat, logs, documentation, commits, or tool
  output.
- When inspecting secret-bearing files, show only filenames, key names, and
  redacted values.
- Do not copy secret-bearing files into task directories, attachments,
  repositories, screenshots, generated artifacts, or documentation.

### Data and source-of-truth safety

- Never create, mutate, seed, delete, or test real business records, customer
  data, inventory records, ERP/accounting records, warehouses, items, stock
  entries, financial records, or production database rows without explicit
  approval for that exact action.
- Dashboards, scanner apps, caches, queues, import helpers, local databases, and
  reporting layers must not become the authoritative source of truth unless
  explicitly approved.
- Preserve established sources of truth. When unsure, document the candidate
  source of truth and ask before changing data ownership.
- Prefer read-only inspection first. For write paths, explain the target system,
  records affected, rollback plan, and validation before proceeding.

### Live services and production-like workloads

- Treat websites, mail, dashboards, ERP/inventory systems, databases, backups,
  live streams, recordings, printers, and internal services as production-like
  unless the user clearly says they are disposable.
- Before restarting, stopping, rebuilding, rebinding ports, changing firewall
  rules, modifying stream or recording state, altering backups, or changing
  service containers, check whether an active workload may be running.
- If interruption, data loss, missed recording, service outage, or network
  exposure is possible, stop and ask for explicit approval.

### Visual and workflow verification

- For UI, website, dashboard, report, document, generated image, layout, stream
  metadata, or other user-visible work, inspect the result before handoff
  whenever possible.
- Prefer browser checks, screenshots, rendered previews, application views,
  logs, smoke tests, or other concrete evidence over code-only inspection.
- Do not claim user-visible work is complete if it has not been viewed or
  smoke-tested. Report exactly what was and was not verified.
- Preserve the user's workflow intent. If a proposed UI, process, or automation
  adds steps, duplicates controls, hides important state, or makes the workflow
  less clear, stop and explain the tradeoff before proceeding.

### Task continuity

- When work is interrupted by troubleshooting, authentication, networking, tool
  setup, or an urgent side quest, record the original goal, repository, branch,
  completed steps, next intended step, and unresolved blocker before switching
  context.
- When returning from an interruption, restate that checkpoint before
  continuing.
- If asked what was being worked on, answer from the checkpoint and current
  repository state rather than guessing.

### Git visibility and handoff

- When the user expects GitHub, another tool, another computer, or a future
  session to see work, local file changes are not enough.
- After explicit approval to publish, commit and push the relevant branch, then
  report the repository, branch, remote, commit, pull request URL when
  applicable, and ahead/behind status.
- If work remains local only, say so clearly and report the exact local path and
  branch.

### Token and time stewardship

- Prefer concrete progress and concise status over speculative expansion.
- Do not continue broad planning, tool exploration, or token-heavy analysis
  after the user has paused, said they did not ask for more, or asked to
  conserve context.
- If the next step is ambiguous but low-risk, state the assumption and proceed
  narrowly. If it could change systems, data, credentials, services, or
  repositories beyond scope, stop and ask.
