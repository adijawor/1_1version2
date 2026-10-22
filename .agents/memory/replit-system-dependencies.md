---
name: Replit system dependencies
description: Preserving Nix-installed tools when validating or replacing Replit configuration.
---

When replacing `.replit`, preserve the `[nix] packages` stanza added by `installSystemDependencies`; otherwise the package may remain in the Nix store but disappear from `PATH`. If it was omitted, reinstall the system dependency to restore the configuration.

**Why:** Full-file configuration replacement can silently remove the environment setup for a system dependency.

**How to apply:** Before validating a replacement `.replit`, read the current file and retain its Nix packages alongside any new workflow or run settings.
