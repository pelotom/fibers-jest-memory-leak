This illustrates a memory leak that occurs when using `jest` with `sqlite3`. After downloading, run `npm install && npm test` to see the error:

```
 FAIL  ./leak.test.js
  ● Test suite failed to run

    EXPERIMENTAL FEATURE!
    Your test suite is leaking memory. Please ensure all references are cleaned.

    There is a number of things that can leak memory:
      - Async operations that have not finished (e.g. fs.readFile).
      - Timers not properly mocked (e.g. setInterval, setTimeout).
      - Keeping references to the global scope.

      at onResult (node_modules/@jest/core/build/TestScheduler.js:188:18)
```
