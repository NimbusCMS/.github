<div align="center">

<img src="https://raw.githubusercontent.com/NimbusCMS/.github/main/brand/avatar.png" width="96" alt="">

# NimbusCMS

**A modern, lightweight PHP CMS — collections, a themeable admin, and a plugin
system you can actually read.**

</div>

---

> ⚠️ **Pre-release.** No tagged version, no upgrade path between versions, no
> password reset. Run it locally, fork it, read it — please don't put a
> client's site on it yet.

## What it is

Most PHP CMSes are either enormous or abandoned. Nimbus is a small, modern,
readable codebase you can hold in your head: PHP 8.2+, PDO, a clean layered
architecture, its own schema via migrations, and a headless-first mindset.

It isn't trying to be WordPress. It's trying to be the CMS you'd be happy to
fork.

## Repositories

| | |
|---|---|
| **[nimbus](https://github.com/NimbusCMS/nimbus)** | The CMS core |
| **[plugin-markdown](https://github.com/NimbusCMS/plugin-markdown)** | Markdown field type — the official reference plugin |
| **[.github](https://github.com/NimbusCMS/.github)** | Community health files and brand assets |

## Plugins

Plugins are ordinary Composer packages:

```bash
composer require nimbuscms/markdown
```

Discovery is Composer's `installed.json`. There's no upload step and no
in-admin installer, because downloading and executing arbitrary code needs
signing, compatibility and rollback policies designed first.

Disable a plugin and **your content is safe**: entries using its field type
stay in the database untouched, the admin shows them read-only and names the
missing provider, and saves are refused until it's back. A CMS that loses
content when a plugin is removed isn't one anyone should trust with content.

The plugin surface is deliberately tiny — today a plugin can register field
types, and that's it. Each further capability gets added alongside a plugin
that actually needs it, never as a batch of extension points designed in
advance. See
[ADR 0001](https://github.com/NimbusCMS/nimbus/blob/main/docs/adr/0001-plugin-contract.md).

## Contributing

Issues, discussion and pull requests are welcome from anyone. You don't need to
be in this organization to write a plugin — plugins live in your own account.

Read [CONTRIBUTING](https://github.com/NimbusCMS/.github/blob/main/.github/CONTRIBUTING.md)
first; for anything beyond a small fix, open an issue before writing code. The
most common reason a pull request gets turned down is that it adds a good
feature the project deliberately doesn't want.

Found a security issue? [Report it privately](https://github.com/NimbusCMS/nimbus/security/advisories/new)
— never in a public issue.

## What lives here

Only **officially maintained** Nimbus software: core, official plugins and
themes, documentation and tooling.

Community plugins and themes stay in their authors' own accounts. They can be
listed in the future Nimbus directory without moving here — *listed* does not
mean *maintained by Nimbus*. A community project joins this organization only
when Nimbus deliberately takes on ongoing maintenance, and only with the
author's agreement.
