# Security policy

## Reporting a vulnerability

**Please do not open a public issue.**

Report privately through
[GitHub Security Advisories](https://github.com/NimbusCMS/nimbus/security/advisories/new),
which lets us discuss and prepare a fix without the details being public first.

Useful to include: what the issue is, how to reproduce it, which version you
tested, and what an attacker could achieve. A proof of concept helps.

Expect an acknowledgement within a few days. You will be credited in the
advisory unless you would rather not be.

## Supported versions

NimbusCMS is pre-release. There is **no tagged release and no upgrade path
between versions yet**, so only `main` is supported.

## Known limitations

Stated plainly, because pretending otherwise would be worse:

- no tagged release, no upgrade path, no backup tooling;
- no password reset flow;
- the Content-Security-Policy still allows `'unsafe-inline'` for scripts;
- forwarded headers are ignored unless `TRUSTED_PROXIES` is configured — that
  is the safe default, but it means a misconfigured deployment behind a proxy
  will throttle logins by proxy IP.

Nimbus is not production-ready. Run it locally, fork it, read it — please do not
put someone's business on it yet.
