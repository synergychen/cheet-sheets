# Unix Cheet Sheet

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
