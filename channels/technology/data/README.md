# Technology data — what goes where

Not sure? Drop it in the repo-root `inbox/` instead and run `/file-inbox`.
**Never** upload passwords, API keys, or recovery codes — reference where they
live (password manager) instead.

| Subfolder | Drop here | Typical source |
|---|---|---|
| `access/` | Who-has-access-to-what exports, admin lists | Google Workspace/M365 admin, password-manager reports |
| `website/` | Hosting/DNS notes, speed/uptime exports | Registrar, PageSpeed/Lighthouse |
| `security/` | MFA status exports, security reports, phishing-test results | Admin consoles |
| `backups/` | Backup configs, restore-test notes | Backup tool |
| `it-vendors/` | Hosting/domain/IT support agreements | Email/contract folder |

The canonical tool inventory is shared with Operations at
`channels/operations/data/systems/`. After dropping: `/it-security-check`.
