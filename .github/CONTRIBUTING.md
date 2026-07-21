# Contributing to NimbusCMS

Thanks for being here. Issues, discussion and pull requests are all welcome,
from anyone.

## Before writing code

For anything beyond a small fix, **open an issue first**. Nimbus is small on
purpose, and the most common reason a pull request gets turned down is that it
adds a good feature the project deliberately does not want. A short
conversation up front saves you the work.

Explicitly out of scope, and unlikely to be accepted: a dependency-injection
container, an ORM, a framework, a generic service locator, or a broad
extension API added before something concrete needs it.

## Working on a change

```bash
docker compose up -d
docker compose exec app php bin/nimbus install
docker compose exec app composer check   # PHPStan level 6 + the full test suite
```

Every pull request must:

- **pass CI** — static analysis and tests, no exceptions;
- **come with tests** when it changes behaviour;
- **stay focused** — one concern per pull request, so review and `git bisect`
  both stay useful;
- **explain the why** in the description. What changed is visible in the diff;
  why it changed is not.

## Code style

Match the surrounding code. A few conventions worth naming:

- `declare(strict_types=1);` in every file;
- comments explain **why**, not what — if a line needs a comment to say what it
  does, prefer clearer code;
- no `header()`, `echo` or `exit` in controllers: build a `Response` and return
  it;
- writes go through services, never straight to a repository from a controller;
- the database is the authority on invariants — prefer a unique index over a
  read-then-write check.

## Writing a plugin

You do not need to contribute to this organization to write a plugin. Plugins
are ordinary Composer packages that live in your own account. See
[ADR 0001](https://github.com/NimbusCMS/nimbus/blob/main/docs/adr/0001-plugin-contract.md)
for the contract and
[plugin-markdown](https://github.com/NimbusCMS/plugin-markdown) for a worked
example.

## Reporting security issues

Do not open a public issue — see [SECURITY.md](SECURITY.md).
