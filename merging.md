# Merging in Git

Merging is the process of combining changes from one branch into another. It is commonly used to integrate completed features or updates into the main branch.

For example, after finishing work on a feature branch, you can merge it into the main branch to include your changes in the project.

## Common Git Commands

**Switch to the target branch:**

```bash
git switch main
```

**Merge another branch into the current branch:**

```bash
git merge feature-branch
```

**Delete a branch after merging:**

```bash
git branch -d feature-branch
```

**Push the updated branch to the remote repository:**

```bash
git push origin main
```

## Types of Merging

**Fast-Forward Merge:**

A Fast-Forward Merge happens when the target branch has no new commits since the feature branch was created. Git simply moves the target branch pointer forward.

**Three-Way Merge:**

A Three-Way Merge happens when both branches have new commits. Git uses the common ancestor and the latest commits from both branches to combine the changes. This may create a merge commit.

## Merge Conflicts

A Merge Conflict occurs when Git cannot automatically combine changes from different branches. This usually happens when two branches modify the same lines of a file or when one branch deletes a file that another branch modifies.

Git marks the conflicting sections in the file using special markers:

```text
<<<<<<< HEAD
Changes from the current branch
=======
Changes from the branch being merged
>>>>>>> feature-branch
```

To resolve a merge conflict:

1. Open the file containing the conflict.
2. Review both versions of the conflicting content.
3. Decide which changes to keep or combine them manually.
4. Remove the conflict markers.
5. Save the file.
6. Stage the resolved file using `git add`.
7. Complete the merge by creating a commit if required.

## Pull Requests

A Pull Request (PR) is a request to merge changes from one branch into another, usually through a platform such as GitHub.

Pull Requests allow team members to:

- Review code before merging.
- Discuss proposed changes.
- Identify potential problems.
- Suggest improvements.
- Approve changes before they are merged.

A Pull Request does not automatically merge branches. It provides an opportunity for review and approval before the changes are integrated into the target branch.
