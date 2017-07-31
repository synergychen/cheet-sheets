# Unix Cheet Sheet

## Table of Contents

* [du](#list-file-sizes)
* [ln](#create-symbolic-link)
* [lsof](#find-process-by-port)

## List File Sizes

List file sizes under current directory in ascending order.

```
du -sh * | sort -h
```

## Find Process By Port

List all processes listening to port `3000`. Could be used to find and kill hidden processes running on specific port.

```
lsof -i :3000
```

## Create Symbolic Link

Create a reference to file or dir, and it will be remain but not reference origin anymore when origin is removed.

```
ln -s <path/to/origin> <path/to/linked-file>
```

## Authorize User to SSH Server

Append pub key to `.ssh/authorized_keys`.
