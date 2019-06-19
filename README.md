# shadow-cljs null pointer exception
This is a minimal reproducible example of a null pointer exception occuring
during compilation. The issue shows up for the library nebula.gl which is a
library built on deck.gl which is built on react-map-gl.
## Setup
```
$ npm install
$ npx shadow-cljs watch app
```
## Error
```
[:app] Compiling ...
[:app] Build failure:
failed to convert sources
{:tag :shadow.build.closure/convert-error, :sources [[:shadow.build.npm/resource "node_modules/nebula_DOT_gl/dist/lib/style.js"] [:shadow.build.npm/resource "node_modules/@babel/runtime/helpers/interopRequireDefault.js"] [:shadow.build.npm/resource "node_modules/@babel/runtime/helpers/classCallCheck.js"]
...
]}
ExceptionInfo: failed to convert sources
	shadow.build.closure/convert-sources-simple*/fn--10878 (closure.clj:1813)
	shadow.build.closure/convert-sources-simple* (closure.clj:1807)
...
Caused by:
NullPointerException: 
	com.google.common.base.Preconditions.checkNotNull (Preconditions.java:877)
	com.google.javascript.jscomp.RemoveUnusedCode$ClassSetupCall.removeInternal (RemoveUnusedCode.java:2496)
	com.google.javascript.jscomp.RemoveUnusedCode$Removable.remove (RemoveUnusedCode.java:1647)
...
```
