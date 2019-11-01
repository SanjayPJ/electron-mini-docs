## Working with Electron Menus

```
const {app, BrowserWindow, Menu} = require('electron')

```

*Next, near the bottom of our createWindow() function, we add:*

```
function createWindow () {

     let menuTemplate = [
      {
          label: 'Menu',
          submenu: [
              {label:'Adjust Notification Value'},
              {
                label:'CoinMarketCap',
                click() { 
                    shell.openExternal('http://coinmarketcap.com')
                },
                accelerator: 'CmdOrCtrl+Shift+C'
            },
            {type:'separator'},  // Add this
            {
                label:'Exit', 
                click() { 
                    app.quit() 
                } 
            }
          ]
      },
      {
        label: 'Info'
      }
  ];

  if(process.env.NODE_ENV !== 'production'){
    menuTemplate.push({
      label: 'Developer Tools',
      submenu:[
        {
          role: 'reload'
        },
        {
          label: 'Toggle DevTools',
          accelerator:process.platform == 'darwin' ? 'Command+I' : 'Ctrl+I',
          click(item, focusedWindow){
            focusedWindow.toggleDevTools();
          }
        }
      ]
    });
  }

let menu = Menu.buildFromTemplate(menuTemplate)

  Menu.setApplicationMenu(menu); 

}
```

- *The label property defines the name that shows up in the actual menu of our app.*
- *So, to make a menu item clickable, we simply add a comma after the label value, and reference click() { }.*
- *We simply add the accelerator property and define the keyboard shortcut*
- *We just add an object with a property of type and a value of separator.*
