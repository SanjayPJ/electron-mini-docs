## Notification

```
const notification = {
    title: 'BTC Alert',
    body: 'BTC just beat your target price!',
    icon: path.join(__dirname, '../assets/images/btc.png')
}

const myNotification = new window.Notification(notification.title, notification)
```
