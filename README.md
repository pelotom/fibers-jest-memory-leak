This illustrates a memory leak that occurs when using `jest` with `node-fibers` (see https://github.com/laverdet/node-fibers/issues/441). Run

```
npm test
```

to see the memory grow by 3-4 MB between each test. Run

```
npm test --detectLeaks
```

for a yes/no indication about the presence of leaks. Commenting out the first line of `includes.js`, which simply requires `fibers`, eliminates the leak.

### Update

Per [this comment](https://github.com/laverdet/node-fibers/issues/441#issuecomment-643467308), adding `-r fibers` as a node option to preload Fibers solves the problem! 🎉