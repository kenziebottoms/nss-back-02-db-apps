# Authentication with `bcrypt` and `passport`

```bash
npm i passport bcrypt-nodejs express-session body-parser
```

## `app.js`:
```js
const session = require('express-session');
const passport = require('passport');
const bodyParser = require('body-parser');

app.use(session({
  secret: 'keyboard cat',
  resave: true,
  saveUninitialized: true
}));

require('./server/config/passport-strat.js');
app.use(passport.initialize());
app.use(passport.session());
app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());
```

## [`server/config/passport-strat.js`](passport-strat.sample.js)

## [`server/ctrl/authC.js`](authCtrl.sample.js)