<div align="center">

<img src="https://raw.githubusercontent.com/NimbusCMS/.github/main/brand/avatar.png" width="96" alt="">

# NimbusCMS

**A modern, lightweight PHP CMS — collections, a themeable admin, and a plugin
system you can actually read.**

**[🧹 Try the live demo →](https://demo.nimbuscms.dev/admin)**
sign in with `demo@nimbuscms.dev` / `explore-nimbus-demo` — full admin, resets hourly
· **[nimbuscms.dev](https://nimbuscms.dev)** (site + docs)

</div>

---

> 🚀 **Beta — [`0.1.0`](https://github.com/NimbusCMS/nimbus/releases/tag/v0.1.0), the first tagged release.**
> It's `0.x`, so the plugin API may still change between minor releases, and there's
> no automatic upgrade path yet. Run it, fork it, build on it — just pin your version.

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
| **[plugin-seo](https://github.com/NimbusCMS/plugin-seo)** | SEO structured data (JSON-LD) for public pages |
| **[plugin-analytics](https://github.com/NimbusCMS/plugin-analytics)** | Privacy-first, first-party analytics |
| **[plugin-api-advanced](https://github.com/NimbusCMS/plugin-api-advanced)** | Advanced API features (a security audit log) |
| **[plugin-inventory](https://github.com/NimbusCMS/plugin-inventory)** | Ledger-based stock, agent-drivable over MCP |
| **[plugin-commerce](https://github.com/NimbusCMS/plugin-commerce)** | Orders + checkout, reserving stock through Inventory |
| **[plugin-storefront](https://github.com/NimbusCMS/plugin-storefront)** | The public, themed shop — catalog, cart + checkout over the Inventory/Commerce ports |
| **[theme-docs](https://github.com/NimbusCMS/theme-docs)** | Zero-JS docs + marketing theme |
| **[theme-cafe](https://github.com/NimbusCMS/theme-cafe)** | A warm small-business / café theme |
| **[theme-aurora](https://github.com/NimbusCMS/theme-aurora)** | A magical-sky storefront theme (powers the Foodmart grocery) |
| **[nimbuscms-www](https://github.com/NimbusCMS/nimbuscms-www)** | The marketing + docs site, running on Nimbus itself |
| **[demo](https://github.com/NimbusCMS/demo)** | The Fern & Kettle demo site (demo.nimbuscms.dev) |
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

The plugin surface grows **one capability at a time**, each added alongside a
plugin that actually needed it — never a batch of extension points designed in
advance. Today a plugin can register field types, contribute to `<head>` and to a page's
**view-data** (live data into themed pages, [ADR 0027](https://github.com/NimbusCMS/nimbus/blob/main/docs/adr/0027-plugin-view-data-contributions.md)), listen
to and **emit** events, own its migrations + tables, declare a grantable
wildcard-immune capability, expose **MCP tools** that gate on it, serve public
routes, publish **typed service ports** to other plugins, and add
**capability-gated admin pages**. Access to core tables and controllers is
deliberately still not exposed. See
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
