## Sqlite

```
npm install --save-dev electron-rebuild
npm install --save sqlite3
```
*Add this into scripts under package.json*

```
"rebuild": "electron-rebuild -f -w sqlite3"
```

```
npm run rebuild
```

```
var sqlite3 = require('sqlite3').verbose();
var db = new sqlite3.Database('database.db');

db.serialize(function() {
    const information = document.getElementById('information').value;
    sql = "INSERT INTO user_info (info) VALUES ('" + information + "')";
    db.run(sql);
    console.log("Data inserted successfully");
});
```
