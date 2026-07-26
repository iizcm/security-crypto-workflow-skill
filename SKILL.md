---
name: security-crypto-workflow
description: "Safe workflow untuk BIP39 recovery phrase, auto-sweep, dan semua operasi crypto yang melibatkan private key. Menekankan keamanan, verifikasi alamat, dan tidak pernah sweep tanpa konfirmasi eksplisit user."
version: 1.0.0
author: User (iizcm)
license: Proprietary
platforms: [linux, macos, windows]
tags: [[security, crypto, wallet, recovery, sweep]]
---

# Security Crypto Workflow — Skill

Safe workflow untuk BIP39 recovery phrase, auto-sweep, dan semua operasi crypto yang melibatkan private key. Menekankan keamanan, verifikasi alamat, dan tidak pernah sweep tanpa konfirmasi eksplisit user.

## Install

```bash
cp -r <skill-name> ~/.hermes/skills/<skill-path>/
```

Or clone this repository:

```bash
git clone https://github.com/iizcm/security-crypto-workflow-skill.git ~/.hermes/skills/<skill-path>/
```

## Usage

Invoke your AI agent with a clear instruction matching this skill's purpose. The agent will route tasks to this skill when the instruction matches its description or trigger keywords.

Refer to `README.md` in this repository for:
- Detailed step-by-step installation guide
- Bilingual documentation (English + Indonesian)
- Troubleshooting table
- Security best practices
- Customization tips

## Safety rules

- Never commit private keys, seed phrases, API tokens, or personal data to version control
- Use placeholders (`<YOUR_...>`) in all examples and code snippets
- Validate all outputs before acting on them
- Keep real credentials in your runtime's secure credential store only
