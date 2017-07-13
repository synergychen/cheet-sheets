# Git Cheet Sheet

## Exclude Files Locally

To exclude file from showing when `git status`

```
git update-index --assume-unchanged <file name>
```

To undo exclude

```
git update-index --no-assume-unchanged <file name>
```

To view all excluded files

```
git ls-files -v | grep '^[[:lower:]]'
```

## Checkout

```
# checkout previous branch
git checkout -
```
