## IPC (Inter-Process Communication)

*main.js file*

```
const ipc = require('electron').ipcMain

ipc.on('update-notify-value', function (event, arg) {
  win.webContents.send('targetPriceVal', arg)
})
```
*IPC Renderer*

```
const ipc = electron.ipcRenderer
const updateBtn = document.getElementById('updateBtn')

updateBtn.addEventListener('click', function () {
  ipc.send('update-notify-value', document.getElementById('notifyVal').value)

  // Close this window
  var window = remote.getCurrentWindow();
  window.close();
})
```
*IPC On*

```
const ipc = electron.ipcRenderer
ipc.on('targetPriceVal', function (event, arg) {
  //Do something
})
```
