# koa-logger-winston

> [Winston](https://github.com/winstonjs/winston) middleware logger for [Koa](https://github.com/koajs/koa) based on [`express-winston`](https://github.com/bithavoc/express-winston).

Forked from [winston-koa-logger](https://github.com/Carlangueitor/winston-koa-logger) to implement ES7 async/await functions for Koa2

# Instalation
    npm install koa-logger-winston

# Usage
You need to pass a instance of winston to middleware.

```js
const Koa = require('koa');
const logger = require('./logger'); // Winston instance.
const winstonKoaLogger = require('koa-logger-winston');

const app = new Koa();

app.use(winstonKoaLogger(logger));

app.use(async (ctx, next) {
  await next();
  ctx.body = 'Hello World';
});

app.listen(3000);
```
