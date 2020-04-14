# Lit Analyzer bug 55

This is a repro for https://github.com/runem/lit-analyzer/issues/55. Issue is caused because we have 2 Chromecast related types: 
`@types/chromecast-caf-receiver@5.0.4` and `@types/chromecast-caf-sender@1.0.3`.

## Install

```
git clone https://github.com/balloob/lit-analyzer-bug-55.git
cd lit-analyzer-bug-55
npm install
```

## Run

```
› npm run lint

> lit-analyzer-bug@1.0.0 lint /Users/paulus/dev/tmp/lit-analyzer-bug
> lit-analyzer index.js

Analyzing 1 files...
TypeError: Cannot read property 'kind' of undefined
    at isDeclarationNameOrImportPropertyName (/Users/paulus/dev/tmp/lit-analyzer-bug/node_modules/typescript/lib/typescript.js:68044:29)
    at getTypeOfNode (/Users/paulus/dev/tmp/lit-analyzer-bug/node_modules/typescript/lib/typescript.js:65642:17)
    at Object.getTypeAtLocation (/Users/paulus/dev/tmp/lit-analyzer-bug/node_modules/typescript/lib/typescript.js:34498:31)
    at /Users/paulus/dev/tmp/lit-analyzer-bug/node_modules/ts-simple-type/lib/index.cjs.js:599:55
    at Array.map (<anonymous>)
    at toSimpleTypeInternal (/Users/paulus/dev/tmp/lit-analyzer-bug/node_modules/ts-simple-type/lib/index.cjs.js:596:59)
    at toSimpleTypeInternalCaching (/Users/paulus/dev/tmp/lit-analyzer-bug/node_modules/ts-simple-type/lib/index.cjs.js:357:33)
    at /Users/paulus/dev/tmp/lit-analyzer-bug/node_modules/ts-simple-type/lib/index.cjs.js:492:60
    at Array.map (<anonymous>)
    at toSimpleTypeInternal (/Users/paulus/dev/tmp/lit-analyzer-bug/node_modules/ts-simple-type/lib/index.cjs.js:492:51)
```
