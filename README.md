# Task 3. Debug in Node.js

1. Задание https://github.com/rolling-scopes-school/basic-nodejs-2021Q2/blob/master/descriptions/debug-nodejs.md
2. Дата сдачи 20.05.2021 / дата дэдлайна 23.05.2021
3. Самооценка 60 (Обнаружено 10 проблем)

обнаруженные проблемы

1. Не верно подключенный роутер
```
./controllers/usercontroller.js
line 1:
before
var router = Router();
fixed to
var router = require('express').Router();
```

2. Не верное имя подключаемого модуля
```
./controllers/usercontroller.js
line 2:
before
var bcrypt = require('bcrypt');
fixed to
var bcrypt = require('bcryptjs');
```

3. Не верное подключение модуля
```
./controllers/usercontroller.js
line 5:
before
var User = require('../db').import('../models/user');
fixed to
var User = require('../models/user');
```

4. Не верное подключение модуля
```
./controllers/gamecontroller.js
line 2:
before
var Game = require('../db').import('../models/game');
fixed to
var Game = require('../models/game');
```

5. Не реализован экспорт функции
```
./models/game.js
line 1:
before
function(sequelize, DataTypes) {
fixed to
module.exports = function(sequelize, DataTypes) {
```

6. Не верное имя експортируемого модуля
```
./controllers/gamecontroller.js
line 116:
before
module.exports = routers;
fixed to
module.exports = router;
```

7. Добавлен экспорт
```
./db.js
line: 18
added
module.exports = sequelize;
```

8. Не верное имя експортируемого модуля
```
./middleware/validate-session.js
line: 2
before
var User = require('sequelize').import('../models/user');
fixed to
var User = require('../models/user');
```

9. Использование устаревшей логики
```
./db.js
line: 6
warning message : sequelize deprecated String based operators are now deprecated. Please use Symbol based operators for better security
fixed
operatorsAliases: false
```

10. Добавлены точки с запятыми
```
./app.js: 5,15
./db.js: 7, 17
./controllers/gamecontroller.js: 19,20,36,37,59,60,90,91,113,114
./controllers/usercontroller.js: 26,27,48,49
./models/game.js: 37
./models/user.js: 25
```


## Installing NPM modules

```
npm install
```

## Running application

```
npm start
```
