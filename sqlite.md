## Sqlite

*Add this into scripts under package.json*

```
"scripts": {
   "postinstall": "install-app-deps"
   ...
}
```

```
npm install --save-dev electron-builder
npm install --save sqlite3
npm run postinstall
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
*Loop Through*

```
db.serialize(function() {
    db.each("SELECT rowid AS id, info FROM user_info", function(err, row) {
        // console.log(row.id + ": " + row.info);
        console.log(row);
    });
});
```
