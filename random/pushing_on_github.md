# Git Index Mechanics & CLI Authentication Caching

## The Concept
GitHub deprecate raw password authentication via the CLI in favor of Personal Access Tokens (PATs) to prevent credential leakage. Additionally, files modified in the working directory reside in an "untracked" or "unstaged" state until explicitly moved to the staging index. A commit cannot capture modifications outside this index.

## The Commands & Configurations

```bash
# 1. Stage untracked working directory files to the index
git add .

# 2. Commit the staged index to local history
git commit -m "upd: descriptive message"

# 3. Configure local Git client to cache PAT credentials persistently
git config --global credential.helper store