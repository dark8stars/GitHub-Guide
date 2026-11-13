# Branching in Git

Branching is one of the most important features of Git. It allows developers to work on different parts of a project independently without making changes directly to the main branch.

A branch is a separate line of development. This allows team members to work on different features or tasks simultaneously. Once their work is complete, they can integrate their changes into the main branch.

## Common Git Commands

**Create a new branch:**

```bash
git branch feature-branch
```

**Create a new branch and switch to it:**

```bash
git switch -c feature-branch
```

**List all existing branches:**

```bash
git branch
```

**Switch to another branch:**

```bash
git switch main
```

**Push a branch to the remote repository:**

```bash
git push -u origin feature-branch
```

## Benefits of Using Branches

- Prevents direct and unintended changes to the main branch.
- Allows multiple developers to work on different parts of a project simultaneously.
- Makes it easier to manage tasks and develop new features.
- Allows changes to be reviewed and tested before being added to the main branch.
- Improves project organization and team collaboration.

## Typical Branching Workflow



