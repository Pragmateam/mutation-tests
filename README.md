## Patch of stryker
https://github.com/stryker-mutator/stryker/issues/1983

file: `jest-runner/src/jestTestAdapters/JestPromiseTestAdapter.js`

line 5:
```
- const jest_1 = tslib_1.__importDefault(require("jest"));
+ const jest_1 = tslib_1.__importStar(require("jest"))
```

line 17:
```
- return jest_1.default.runCLI(Object.assign(Object.assign({}, (fileNameUnderTest && { _: [fileNameUnderTest], findRelatedTests: true })), { config, runInBand: true, silent: true }), [projectRoot]);
+  return jest_1.runCLI(Object.assign(Object.assign({}, (fileNameUnderTest && { _: [fileNameUnderTest], findRelatedTests: true })), { config, runInBand: true, silent: true }), [projectRoot]);
```


## How to run tests
``` 
npm run mutation
``` 