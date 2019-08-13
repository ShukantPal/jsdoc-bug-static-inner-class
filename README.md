#Bug Demonstration for JSDoc (static inner classes)

JSDoc will give the following error when running `npm run test` on
my machine, which is due to a static inner class:

```
TypeError: Cannot read property 'memberof' of null
    at Parser.astnodeToMemberof (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/parser.js:392:24)
    at addSymbolMemberof (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/handlers.js:268:31)
    at newSymbolDoclet (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/handlers.js:298:13)
    at Parser.<anonymous> (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/handlers.js:365:13)
    at Parser.emit (events.js:203:13)
    at Visitor.visitNode (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/visitor.js:849:20)
    at Visitor.visit (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/visitor.js:759:21)
    at Walker.recurse (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/walker.js:694:42)
    at Parser._walkAst (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/parser.js:305:22)
    at Parser._parseSourceCode (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/parser.js:296:22)
    at Parser.parse (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/lib/jsdoc/src/parser.js:202:22)
    at Object.module.exports.cli.parseFiles (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/cli.js:365:46)
    at module.exports.cli.main (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/cli.js:234:18)
    at Object.module.exports.cli.runCommand (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/cli.js:186:9)
    at /Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/jsdoc.js:93:9
    at Object.<anonymous> (/Users/shukantpal/Web Projects/jsdoc-bug-static-inner-class/node_modules/jsdoc/jsdoc.js:94:3)
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! jsdoc-bug-static-inner-class@1.0.0 test: `jsdoc -c ./.jsdoc.conf.json --verbose`
npm ERR! Exit status 1
npm ERR!
npm ERR! Failed at the jsdoc-bug-static-inner-class@1.0.0 test script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR!     /Users/shukantpal/.npm/_logs/2019-08-13T16_02_36_230Z-debug.log
```
