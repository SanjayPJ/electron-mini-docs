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

### Uncaught ReferenceError: process is not defined

```
  mainWindow = new BrowserWindow({
    webPreferences: {
      preload: path.join(__dirname, 'preload.js'),
      nodeIntegration: true 
    }
  })
```

### Disable Parent Window

```
    parent: mainWindow,
    modal: true, 
```

*Add it into BrowserWindow method*

### Get Current Window and close

```
  var window = remote.getCurrentWindow();
  window.close();
```
