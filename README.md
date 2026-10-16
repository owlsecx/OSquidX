# 🦉 OSquidX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-ONetwork-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OSquidX** — Squid Proxy Configuration Hardening Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

Squid proxy configuration hardening auditor (offline, read-only)

---

## ✨ Features

- Stdlib squid.conf parser — line continuation, include globs (conf.d/*.conf), loop detection, quoted ACL files
- http_access evaluator — allow all, missing deny all, open proxy, CONNECT !SSL_ports, Safe_ports, manager, to_localhost / to_linklocal (cloud metadata SSRF)
- SSL-Bump & TLS — sslproxy_cert_error, DONT_VERIFY_PEER, tls-min-version, weak ciphers, sslcrtd db & CA key perms
- Auth helpers — basic over cleartext, passwd file perms, credentialsttl, LDAP bind secrets, keytab, NTLM
- cachemgr_passwd, ICP / HTCP / SNMP, cache_peer login=, accel vhost relay, privacy headers, logging, cache_dir
- Secrets masked everywhere; --root offline trees; CWE + MITRE
- Export TXT / Markdown / JSON / CSV / SARIF 2.1.0
- Self-test --demo, CI gates --fail-on / --min-severity

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OSquidX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
