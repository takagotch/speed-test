### speed-test
---
https://github.com/sindresorhus/speed-test

```js
// test.js
import test from 'ava';
import execa from 'execa';

test.cb('main', t => {
  const cp = childProcess.spawn('./cli.js', {stdio: 'inherit'});
  
  cp.on();
});


```

```
npm install --global speed-test
speed-test --help
```

```
```


