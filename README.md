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
```
