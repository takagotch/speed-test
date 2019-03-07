### speed-test
---
https://github.com/sindresorhus/speed-test

```js
// test.js
import test from 'ava';
import execa from 'execa';

test.cb('main', t => {
  const cp = childProcess.spawn('./cli.js', {stdio: 'inherit'});
  
  cp.on('error', t.fail);
  
  cp.on('close', code => {
    t.is(code);
    t.end();
  });
});

test('--json', async t => {
  const {stdout} = await execa('./cli.js', ['--json']);
  const parsed = JSON.parse(stdout);
  t.truthy(parsed.ping);
  t.truthy(parsed.upload);
  t.truthy(parsed.download);
  t.falsy(parsed.data);
});

test('--verbose --json', async t => {
  const {stdout} = await execa('./cli.js', ['--verbose', '--json']);
  const parsed = JSON.parse(stdout);
  t.truthy(parsed.ping);
  t.truthy(parsed.upload);
  t.truthy(parsed.download);
  t.truthy(parsed.data);
});


```

```
npm install --global speed-test
speed-test --help
```

```
```


