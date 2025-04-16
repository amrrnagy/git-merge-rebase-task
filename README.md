# git-merge-rebase-task

Git Merge vs. Git Rebase: Key Differences and When to Use Each

Core Concepts
Both commands integrate changes between branches but follow different approaches:
• Merge: Combines branches while preserving their individual histories
• Rebase: Rewrites history to create a linear timeline

Git Merge Explained
How It Works:
- Creates a new "merge commit" that ties both branches together
- Maintains the complete development history
- Non-destructive operation (original commits remain unchanged)

Visual Representation:
    *   Merge commit (combines main and feature)
    |\  
    | * Feature commit 3
    | * Feature commit 2
    * | Main commit 2
    * | Main commit 1

Git Rebase Explained
How It Works:
- Replays your branch's commits on top of another branch
- Creates new commit objects with different hashes
- Results in a perfectly linear history

Visual Representation:
    * Feature commit 3 (new hash)
    * Feature commit 2 (new hash)
    * Main commit 2
    * Main commit 1

Comparison Table
Aspect	Merge	Rebase
History Style	Preserves fork points	Creates a linear timeline
Commit Integrity	Original hashes preserved	Generates new commit IDs
Safety Level	Safe for shared branches	Risky for public branches
Best For	Team collaboration	Local branch cleanup

 
Best Practices
✓ Do Merge When:
  - Integrating into main/develop branches
  - Multiple developers work on the same branch
  - You need audit trails

✓ Do Rebase When:
  - Preparing branches for pull requests
  - Cleaning up local commit history
  - Keeping feature branches updated

✖ Never:
  - Rebase public/shared branches
  - Rebase commits that others depend on
  - Force push rebased branches without warning

Advanced Tips:
• Use `git rebase -i` for interactive history editing
• Try `git merge --no-ff` to preserve merge context
• Consider `git cherry-pick` for selective commits
