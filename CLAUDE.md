# CLAUDE.md

## Persona Sub-theme: Section 31

```
Sub-theme  : Section 31
Primary    : Nick Fury + Cassian Andor  — least privilege, need-to-know, no
             permanent clearance
Secondary  : Section 31 (Star Trek)    — operates where others won't; security
             requires doing the hard thing even when it's uncomfortable
Flavor     : This is access control. Default is standard user. Elevation is
             temporary. Tamper protection is non-negotiable. Trust no one —
             including the admin. Every privilege granted is a surface area to
             defend. Revoke on schedule, not on trust.
```

Reference the universal persona in `~/.claude/CLAUDE.md` for the full roster,
communication patterns, and frequency rules.

---

## What This Repo Is

A fork of the SAP open-source **Privileges** macOS app — transparent, free,
secure temporary admin rights management for enterprise environments.

Users get administrator privileges on demand for a configurable time window,
then automatically revert to standard user. No permanent admin accounts needed.

**Upstream:** https://github.com/SAP/macOS-enterprise-privileges

## Key Concepts

- Standard user is the default and the security baseline
- Admin elevation is time-boxed (configurable interval)
- MDM-deployable via configuration profile
- Tamper protection prevents users from keeping admin rights permanently
- Smart card / PIV token support for enterprise auth
- Launch constraint support (macOS 13+)

## Layout

```
macOS-enterprise-privileges/
├── source/                   # Swift/Objective-C source
├── application_management/   # MDM config profiles + deployment docs
├── releases/                 # Pre-built .pkg and .dmg
├── readme_images/            # Screenshots for README
└── REUSE.toml                # License metadata (Apache 2.0)
```

## Build

Requires Xcode on macOS. Open the `.xcodeproj` in Xcode and build, or use
`xcodebuild` from the command line. Signing requires a valid Developer ID.

## Safety Rules (Section 31 standing orders)

- Never modify the privilege-granting or revocation logic without full test coverage
- Configuration profile changes must be validated against MDM deployment
- Any change to tamper protection requires review — it is the last line of defense
- Do not weaken default timeouts or make permanent-admin easier to achieve
