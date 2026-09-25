# Linux File Permissions Review and Remediation

## Overview

Reviewed and corrected file and directory permissions in a simulated Linux environment to ensure that access matched an organization's security requirements.

Using Linux commands, I identified excessive permissions, applied targeted changes, and verified that authorized users retained the access needed for their work.

## Security Review

The assessment focused on a research team's project directory:

`/home/researcher2/projects`

I used `ls -la` to examine file ownership and permissions, including hidden files.

Three entries required changes:

| File or Directory | Original Permissions | Required Permissions |
|---|---|---|
| `project_k.txt` | `-rw-rw-rw-` | `-rw-rw-r--` |
| `.project_x.txt` | `-rw--w----` | `-r--r-----` |
| `drafts/` | `drwx--x---` | `drwx------` |

The remaining files already met the organization's access requirements and did not require modification.

## Permission Remediation

### Remove Unauthorized Write Access

The file `project_k.txt` allowed other users to modify its contents.

I removed write access for others while preserving the owner's and group's existing permissions.

```bash
chmod o-w project_k.txt
```

**Result:** `-rw-rw-r--`

### Secure the Archived File

The archived file `.project_x.txt` needed to remain readable by the owner and group without permitting modifications.

```bash
chmod u=r,g=r,o= .project_x.txt
```

**Result:** `-r--r-----`

### Restrict Directory Access

The `drafts` directory was intended for the owner only.

I removed the group's existing directory-traversal permission.

```bash
chmod g-x drafts
```

**Result:** `drwx------`

## Verification and Outcome

After applying the permission changes, I reviewed the resulting permission strings to confirm that the files and directory matched the stated access requirements.

The changes:

- Removed unauthorized write access from a project file
- Restricted an archived file to read-only access for the owner and group
- Limited access to a private directory
- Preserved permissions required for authorized work

## Skills Demonstrated

- Linux command-line operations
- Linux file and directory permissions
- Permission auditing
- Access-control remediation
- Least privilege
- `ls -la`
- `chmod`
- Permission verification
- Technical documentation

## Completed Assessment

[View the completed Linux file permissions report](./linux-file-permissions-review-and-remediation.pdf)

## Project Context

This work was completed in a simulated Linux security lab. The scenario and access requirements were provided; the permission review, command execution, remediation, and portfolio report reflect my work.
