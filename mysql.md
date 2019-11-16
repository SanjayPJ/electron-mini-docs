## Mysql Connection

```
npm install mysql
```

*Create connection*

```
var mysql = require('mysql');

var con = mysql.createConnection({
  host: "localhost",
  user: "root",
  password: null,
  database: "myinfo"
});

con.connect(function(err) {
    if (err) throw err
      console.log("Mysql connected successfully");
});
```

*Execute Query*

```
let sql = "INSERT INTO `contacts` (`first_name`, `last_name`, `description`, `id`) VALUES ('" + firstname + "', '" + lastname + "', '" + description + "', NULL);"

 con.query(sql, function (err, result, fields) {
  if (err) throw err;
  console.log(result);
});
```

*Close connection*

```
connection.end();
```
