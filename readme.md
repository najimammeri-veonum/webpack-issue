### Expected behavior

The value of `jsonAsString` in `index.js` should be a string representing the contents of `data.json`.  
No JSON parser should run.

### Observed behavior

Webpack's JSON parser executes.

```
$ npx webpack
Hash: 8147022ef409063f4b9b
Version: webpack 4.25.1
Time: 136ms
Built at: 2018-11-16 10:02:22
  Asset      Size  Chunks             Chunk Names
main.js  4.49 KiB    main  [emitted]  main
Entrypoint main = main.js
[./index.js] 164 bytes {main} [built]
[./node_modules/raw-loader/index.js!./data.json] ./node_modules/raw-loader!./data.json 1.98 KiB {main} [built] [failed] [1 error]

ERROR in ./data.json (./node_modules/raw-loader!./data.json)
Module parse failed: Unexpected token m in JSON at position 0 while parsing near 'module.exports = "{\...'
You may need an appropriate loader to handle this file type.
SyntaxError: Unexpected token m in JSON at position 0 while parsing near 'module.exports = "{\...'
    at JSON.parse (<anonymous>)
    at parseJson (C:\Users\sw42\src\webpack-issue\node_modules\json-parse-better-errors\index.js:7:17)
    at JsonParser.parse (C:\Users\sw42\src\webpack-issue\node_modules\webpack\lib\JsonParser.js:16:16)
    at doBuild.err (C:\Users\sw42\src\webpack-issue\node_modules\webpack\lib\NormalModule.js:445:32)
    at runLoaders (C:\Users\sw42\src\webpack-issue\node_modules\webpack\lib\NormalModule.js:327:12)
    at C:\Users\sw42\src\webpack-issue\node_modules\loader-runner\lib\LoaderRunner.js:370:3
    at iterateNormalLoaders (C:\Users\sw42\src\webpack-issue\node_modules\loader-runner\lib\LoaderRunner.js:211:10)
    at iterateNormalLoaders (C:\Users\sw42\src\webpack-issue\node_modules\loader-runner\lib\LoaderRunner.js:218:10)
    at C:\Users\sw42\src\webpack-issue\node_modules\loader-runner\lib\LoaderRunner.js:233:3
    at runSyncOrAsync (C:\Users\sw42\src\webpack-issue\node_modules\loader-runner\lib\LoaderRunner.js:130:11)
    at iterateNormalLoaders (C:\Users\sw42\src\webpack-issue\node_modules\loader-runner\lib\LoaderRunner.js:229:2)
    at Array.<anonymous> (C:\Users\sw42\src\webpack-issue\node_modules\loader-runner\lib\LoaderRunner.js:202:4)
    at Storage.finished (C:\Users\sw42\src\webpack-issue\node_modules\enhanced-resolve\lib\CachedInputFileSystem.js:43:16)
    at provider (C:\Users\sw42\src\webpack-issue\node_modules\enhanced-resolve\lib\CachedInputFileSystem.js:79:9)
    at C:\Users\sw42\src\webpack-issue\node_modules\graceful-fs\graceful-fs.js:90:16
    at FSReqWrap.readFileAfterClose [as oncomplete] (internal/fs/read_file_context.js:53:3)
 @ ./index.js 1:21-54
```

