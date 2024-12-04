# Mocha CJS/ESM error message issue

See https://github.com/mochajs/mocha/issues/5235

## Running

```
pnpm i
pnpm test
```

```
 Exception during run: TypeError: Unknown file extension ".ts" for /Users/andy/gh/mocha-cjs-esm/test.ts
    at Object.getFileProtocolModuleFormat [as file:] (node:internal/modules/esm/get_format:160:9)
    at defaultGetFormat (node:internal/modules/esm/get_format:203:36)
    at defaultLoad (node:internal/modules/esm/load:141:22)
    at ModuleLoader.load (node:internal/modules/esm/loader:409:7)
    at ModuleLoader.moduleProvider (node:internal/modules/esm/loader:291:45)
    at link (node:internal/modules/esm/module_job:76:21) {
  code: 'ERR_UNKNOWN_FILE_EXTENSION'
}
```

If you comment out the `chai` import and the `expect` assertion in `test.ts`, running the test passes.
