# Changes Directory

This directory contains all change requests for the organization. Change requests are organized by their current status.

## Directory Structure

- **`pending/`** - Change requests that are being prepared or awaiting CAB review
- **`approved/`** - Change requests that have been approved by CAB and are scheduled for implementation
- **`implemented/`** - Change requests that have been successfully implemented
- **`archived/`** - Historical change requests organized by year

## Naming Convention

Change request files should follow this naming pattern:
```
CR-YYYY-NNNN-brief-description.md
```

Where:
- `CR` = Change Request prefix
- `YYYY` = Year
- `NNNN` = Sequential number (e.g., 0001, 0002)
- `brief-description` = Short kebab-case description

**Examples**:
- `CR-2025-0001-database-upgrade.md`
- `CR-2025-0002-api-security-patch.md`
- `CR-2025-0003-load-balancer-config.md`

## Workflow

```
pending/ → approved/ → implemented/ → archived/
```

### 1. Pending Phase
- Create change request from template
- Document all details
- Test in non-production environments
- Gather test evidence

### 2. Approved Phase
- CAB has reviewed and approved
- Implementation scheduled
- Stakeholders notified

### 3. Implemented Phase
- Change has been executed
- Validation completed
- Post-implementation review done

### 4. Archived Phase
- Move older changes here for historical reference
- Organize by year for easy retrieval

## Moving Between States

Use git to move files between directories to maintain history:

```bash
# Move from pending to approved
git mv changes/pending/CR-2025-0001-example.md changes/approved/

# Move from approved to implemented
git mv changes/approved/CR-2025-0001-example.md changes/implemented/

# Archive implemented changes at end of year
git mv changes/implemented/CR-2025-0001-example.md changes/archived/2025/
```

## Tips

- Keep the change request up-to-date as it moves through phases
- Add implementation notes and actual results during execution
- Complete post-implementation review before archiving
- Reference change requests in commit messages across repositories
- Link related change requests together

---

Place `.gitkeep` files in empty directories to track them in git if needed.
