## What is this?

This is @bcrypt's janky twitter replacement see [diracdeltas/tweets: janky twitter replacement.](https://github.com/diracdeltas/tweets).

## Setup

- fork https://github.com/diracdeltas/tweets
- in your fork:

```
git reset --hard d10b092
git push -f origin main
```

## Stuff you can do

- to post:

```
git commit -m "your post" --allow-empty
git push
```

- to follow someone:

```
git remote add <git name> <their fork of diracdelta's repo>
git fetch <git name>
```

- to follow everybody using GitHub:
  `./follow-everybody.bash`

- to repeat someone else's utterance:

```
git cherry-pick -x <their commit hash>
```

- [people to follow](https://github.com/diracdeltas/tweets/network/members)

- to refresh your timeline and view it:

```
git fetch --all && git rev-list --all --remotes --pretty | less
```

- some alternative ways to view your timeline (use `git show <commit hash>` to
  show the full "tweet"):

```
git log --format="format:%Cred%cd %Cblue%h %Cgreen%cn%Creset: %s" --all --date=iso-local
git log --graph --all --decorate --oneline
```

- to get verified (GitHub-only):

1. [follow github's own verification instructions and make your commit email match your GPG key email](https://docs.github.com/en/authentication/managing-commit-signature-verification/about-commit-signature-verification)
2. `git commit -S -m "your post" --allow-empty` from now on

- to encrypt a message:

see `encrypt using the public key of a github user` in https://sshenc.sh/ or
use your favorite key distribution mechanism to get their public key.

## Cheatcodes

```shell
make post $"Your sage wisdom"
```

---

```shell
make refresh
```

---

```shell
make timeline
```

_OR_

```shell
make timeline-short
```

_OR_

```shell
make timeline-graph
```
