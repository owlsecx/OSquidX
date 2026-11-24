# 🦉 OSquidX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSquidX** — Squid Proxy Configuration Hardening Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview


OSquidX is an offline, read-only Squid proxy configuration hardening auditor for both forward and reverse deployments. It parses squid.conf (with include globs and continuations), evaluates http_access rules for open-proxy and SSRF exposure, and reviews SSL-Bump, authentication, cache-manager and peer settings. Secrets are masked throughout, and findings mapped to CWE/MITRE are exportable as TXT, Markdown, JSON, CSV or SARIF.

---

## ✨ Features


- Stdlib squid.conf parser with line continuation, include globs (conf.d/*.conf) and loop detection
- http_access evaluator: allow-all, missing deny-all, open proxy, CONNECT !SSL_ports, cloud-metadata SSRF
- SSL-Bump & TLS review: sslproxy_cert_error, DONT_VERIFY_PEER, tls-min-version, weak ciphers, CA key perms
- Auth helper checks: basic over cleartext, passwd file perms, credentialsttl, LDAP/NTLM bind secrets
- cachemgr_passwd, ICP/HTCP/SNMP, cache_peer login=, accel vhost relay and logging/privacy checks
- Secrets masked, offline --root trees, CWE+MITRE mapping and TXT/MD/JSON/CSV/SARIF export with CI gates

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage


```bash
./OSquidX --scan -f sarif -o squid.sarif
./OSquidX -c /etc/squid/squid.conf --min-severity medium
./OSquidX -r /mnt/image --fail-on high --json
./OSquidX --demo
./OSquidX --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OSquidX --help   # watch every network call
firejail --net=none ./OSquidX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
