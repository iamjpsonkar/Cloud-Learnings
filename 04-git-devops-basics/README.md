# Git and DevOps Basics

Version control is the foundation of modern software delivery. Every cloud deployment, infrastructure change, and configuration update should flow through Git. This section covers Git fundamentals, GitHub collaboration workflows, and SSH key management — the daily tools of cloud and DevOps engineering.

---

## Topics

| File | What it covers |
|------|---------------|
| [git-basics.md](git-basics.md) | Core Git concepts, everyday commands, branching, merging, rebasing, history |
| [github-workflow.md](github-workflow.md) | Pull request workflow, code review, branch protection, GitHub Actions basics |
| [ssh-keys.md](ssh-keys.md) | SSH key generation, GitHub/GitLab authentication, multiple identities, agent |

---

## Minimum Competency

Before working on production infrastructure repositories, be comfortable with:

- [ ] Initialise a repo, stage files, make commits with meaningful messages
- [ ] Create, switch, and merge branches
- [ ] Understand the difference between `merge` and `rebase`
- [ ] Resolve merge conflicts in a text editor
- [ ] Use `git log`, `git diff`, `git status` fluently
- [ ] Undo changes safely: `git restore`, `git reset`, `git revert`
- [ ] Push to and pull from a remote (`origin`)
- [ ] Open a pull request, review code, and merge via GitHub
- [ ] Configure SSH key authentication with GitHub (no password prompts)
- [ ] Understand `.gitignore` patterns

---

## Git Mental Model

```
Working Directory    Staging Area (Index)     Local Repository       Remote (GitHub)
      │                     │                        │                     │
      │── git add ─────────▶│                        │                     │
      │                     │── git commit ─────────▶│                     │
      │                     │                        │── git push ─────────▶│
      │◀── git restore ──────│                        │                     │
      │                     │                        │◀── git fetch ────────│
      │◀──────────────────── git checkout ────────────│                     │
      │◀──────────────────── git merge ───────────────│                     │
```

---

## References

- [Pro Git book (free)](https://git-scm.com/book/en/v2)
- [GitHub documentation](https://docs.github.com/)
- [Oh My Git! — visual Git learning game](https://ohmygit.org/)
- [Git flight rules](https://github.com/k88hudson/git-flight-rules)
---

← [Previous: Networking](../03-networking/README.md) | [Home](../README.md) | [Next: AWS →](../05-aws/README.md)
