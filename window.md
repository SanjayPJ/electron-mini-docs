## Creating Window

*From a button*

```
      const electron = require('electron')
      const path = require('path')
      const BrowserWindow = electron.remote.BrowserWindow

      const addItem = document.getElementById('add-item')
      
      addItem.addEventListener('click', function (event) {
        let win = new BrowserWindow({  width: 300, height: 200, })
        win.setMenuBarVisibility(false)
        win.on('close', function () { win = null })
        win.loadURL(path.join('file://', __dirname, 'add.html'))
        win.show()
      })

```

*Inside main.js*

```
function createAddWindow(){
  addWindow = new BrowserWindow({
    width: 300,
    height: 200,
    parent: mainWindow,
    modal: true, 
    webPreferences: {
      preload: path.join(__dirname, 'preload.js'),
      nodeIntegration: true
    }
  })

  addWindow.setMenuBarVisibility(false)

  addWindow.loadFile('add.html')

  addWindow.on('closed', function () {
  addWindow = null
  })
}

```
