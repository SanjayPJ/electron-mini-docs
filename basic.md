## Basics

### Adding Icon

```
  mainWindow = new BrowserWindow({
    width: 1100,
    height: 600,
    icon: path.join(__dirname, 'img/icon.png'),
    webPreferences: {
      preload: path.join(__dirname, 'preload.js')
    }
  })
```
