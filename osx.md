# OSX Cheet Sheet

## Hide App From `Cmd + Tab`

Open and edit app plist file:

```
vim /Applications/<app_name>.app/Contents/Info.plist
```

Add following key value to plist `dict`:

```
<key>LSUIElement</key>
<string>1</string>
```

Restart app.

